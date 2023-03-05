# Spring_MultipartFile

파일 업로드 

파일업로드시에 HTML 폼 전송 방식은 multipart/form-data 를 사용한다.

spring.servlet.multipart.enabled=true. (기본 true) 

위의 해당 기능이 false가 되어잇으면 Was자체에서 multipart기능을 지원하지않는다. 
Request.getParameter 에 값이 안들어옴.


추가옵션 
-
spring.servlet.multipart.max-file-size=1MB
spring.servlet.multipart.max-request-size=10MB

스프링은 MultipartFile 이라는 인터페이스로 멀티파트 파일을 매우 편리하게 지원한다.  아래와 같이 받을 수 있다.

@PostMapping("/upload")
      public String saveFile(@RequestParam String itemName,
                             @RequestParam MultipartFile file, HttpServletRequest
  request) throws IOException {
 
			로직

}

MultipartFile 주요 메서드 
file.getOriginalFilename() : 업로드 파일 명 
file.transferTo(...) : 파일 저장 

