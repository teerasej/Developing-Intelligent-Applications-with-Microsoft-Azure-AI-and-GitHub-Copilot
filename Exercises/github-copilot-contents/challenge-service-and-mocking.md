
# Challenge: Service and Mocking

## Exercise 1: Generate a service class

1. Try to create a service class **ProfileService.java** that do following things: 
    1. Get json from `https://651d740c44e393af2d59d2b4.mockapi.io/api/profiles` then return out from get request with `/profiles` endpoint.
    2. The template of json result
        ```json
        [
            {
                "name": "John Doe",
                "age": 30
            }
        ]
        ```

2. it should similar to this:

```java
package th.in.nextflow.NextflowBoot;

import org.springframework.stereotype.Service;
import org.springframework.web.client.RestTemplate;
import java.util.List;
import java.util.Arrays;


@Service
public class ProfileService {

    private static final String PROFILE_API_URL = "https://651d740c44e393af2d59d2b4.mockapi.io/api/profiles";
    private final RestTemplate restTemplate;

    public ProfileService(RestTemplate restTemplate) {
        this.restTemplate = restTemplate;
    }

    public List<Profile> getProfiles() {
        Profile[] profiles = restTemplate.getForObject(PROFILE_API_URL, Profile[].class);
        return Arrays.asList(profiles);
    }
}


public class Profile {
    private String name;
    private int age;

    // Getters and Setters
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

## Exercise 2: Create a controller to use the service

1. Create a new controller **ProfileController.java** that use the service to get the profiles from the service. it should be saved in package `th.in.nextflow.NextflowBoot.controller`.

    > **Hint:** you might use Copilot chat for more precise result (such as `@workspace create a controller 'profilecontroller' that provide url to get profiles as json array from service`)

2. The controller should operate similar to this:


```java
package th.in.nextflow.NextflowBoot.controller;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;
import th.in.nextflow.NextflowBoot.ProfileService;
import th.in.nextflow.NextflowBoot.Profile;

import java.util.List;

@RestController
public class ProfileController {

    @Autowired
    private ProfileService profileService;

    @GetMapping("/profiles")
    public List<Profile> getProfiles() {
        return profileService.getProfiles();
    }
}
```

## Exercise 3: Test the controller

1. Try to create test for the controller **ProfileControllerTest.java** that use the service to get the profiles from the service. 

    > **Hint:** you might use Copilot chat for more precise result (such as `@workspace create a test class 'profilecontrollertest' that test the profilecontroller`)

2. The test should operate similar to this:

```java
package th.in.nextflow.NextflowBoot.controller;


import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;
import org.mockito.InjectMocks;
import org.mockito.Mock;
import org.mockito.MockitoAnnotations;
import org.springframework.http.MediaType;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.setup.MockMvcBuilders;
import th.in.nextflow.NextflowBoot.Profile;
import th.in.nextflow.NextflowBoot.ProfileService;
import java.util.Arrays;
import java.util.List;
import static org.mockito.Mockito.when;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.content;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.status;





public class ProfileControllerTest {

    private MockMvc mockMvc;

    @Mock
    private ProfileService profileService;

   
    

    @Test
    public void testGetProfiles() throws Exception {
        Profile profile1 = new Profile("John", 30);
        Profile profile2 = new Profile("Jane", 20);
        List<Profile> profiles = Arrays.asList(profile1, profile2);

        when(profileService.getProfiles()).thenReturn(profiles);

        mockMvc.perform(get("/profiles")
                .contentType(MediaType.APPLICATION_JSON))
                .andExpect(status().isOk())
                .andExpect(content().json("[{'firstName':'John','lastName':'Doe'},{'firstName':'Jane','lastName':'Doe'}]"));
    }
}
```

> **Note:** You might need to modify some part of `Profile` class