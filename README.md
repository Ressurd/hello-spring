# hello-spring
hello-spring

## 스프링 연습용


### 초기세팅
#### https://start.spring.io
![image](https://user-images.githubusercontent.com/28950131/126970430-22950ea4-5693-4388-b4bd-513c9542aca8.png)


## 단축키
##### ctrl + p -> 파라미터 보기


## 소스코드

```java
@GetMapping("hello")
    public String hello(Model model){
        model.addAttribute("data", "hello!!");
        return "hello";
    }
```

@GetMapping -> 웹브라우저에서 url 경로 관련 매핑해줌
return -> 리턴한 부분의 정적 템플릿 페이지를 찾아감.

```html
<html xmlns:th="http://www.thymeleaf.org">
<body>
<p th:text="'hello ' + ${name}">hello! empty</p>
</body>
```

thymeleaf 문법중 하나, p 태그의 th:text 부분인데,
이 부분 같은 경우 java 소스에서 addAttribute에서 넘겨주는 부분을 받아준다.

```java
@GetMapping("hello-mvc")
    public String helloMvc(@RequestParam("name") String name, Model model){
        model.addAttribute("name", name);
        return "hello-template";
    }
```
해당하는 소스부분인데, 이중 model.addAttribute 부분.

