# Spring Boot, React.js & AWS S3 Full Stack Development

Make access keys 
https://youtu.be/9i1gQ7w2V24?t=2266

Pgadmin URL
http://localhost/browser/

## Refactors 
Put the refactors in a todo file 

Save in public github 

Have to create a database customer
	Get credentials from environment 
		Table Customer 
		jdbc-url: jdbc:postgresql://${POSTGRES_HOSTNAME}/${POSTGRES_DB}
        username: ${POSTGRES_USER}
        password: '${POSTGRES_PASSWORD}'
	Refactor 
		Put in growing with resources 
			https://stackoverflow.com/a/55919807
		https://medium.com/cwi-software/versionar-sua-base-de-dados-com-spring-boot-e-flyway-be4081ddc7e5
		
Make testcontainer work 
https://github.com/testcontainers/testcontainers-java/tree/main/examples/linked-container
https://java.testcontainers.org/examples/
https://java.testcontainers.org/supported_docker_environment/continuous_integration/dind_patterns/
https://code.visualstudio.com/remote/advancedcontainers/use-docker-kubernetes		
		
Have test work again 	
	Tem test novo na main branch

Ver se tem Spring Integration test	
	https://www.baeldung.com/spring-5-webclient
	https://www.baeldung.com/rest-assured-tutorial
	https://www.baeldung.com/integration-testing-in-spring#mockmvc-limitations
	https://www.springboottutorial.com/integration-testing-for-spring-boot-rest-services
		
https://www.baeldung.com/spring-profiles#profiles-in-spring-boot
Para usar o mock S3 
Tambem colocar o mock s3 no service profile 
S3Client 
    @Bean
    public S3Client s3Client() {
        if (mock) {
            return new FakeS3();
        }
        return S3Client.builder()
                .region(Region.of(awsRegion))
                .build();
    }
	
https://www.baeldung.com/spring-boot-thymeleaf-image-upload
@Controller public class UploadController {

    public static String UPLOAD_DIRECTORY = System.getProperty("user.dir") + "/uploads";

    @GetMapping("/uploadimage") public String displayUploadForm() {
        return "imageupload/index";
    }

    @PostMapping("/upload") public String uploadImage(Model model, @RequestParam("image") MultipartFile file) throws IOException {
        StringBuilder fileNames = new StringBuilder();
        Path fileNameAndPath = Paths.get(UPLOAD_DIRECTORY, file.getOriginalFilename());
        fileNames.append(file.getOriginalFilename());
        Files.write(fileNameAndPath, file.getBytes());
        model.addAttribute("msg", "Uploaded images: " + fileNames.toString());
        return "imageupload/index";
    }
}

Remove this 3 constructor in customer and make a method who create a customer in test
		
Remove commandliner
	start with 3 customer dont use for test 

Use jpa 
	Already exist a CustomerRepository

Voltar a fazer o video 
https://youtu.be/9i1gQ7w2V24?t=7992

Make cypress run against mock data in the front 
	react is correct ?

## Source; 
https://www.youtube.com/watch?v=9i1gQ7w2V24&ab_channel=Amigoscode

https://github.com/amigoscode/full-stack-professional

