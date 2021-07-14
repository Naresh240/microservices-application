# microservices-application
  ![image](https://user-images.githubusercontent.com/58024415/125563123-0480c2a0-cba4-4f92-b1df-a164e7df00ec.png)
# Application Architecture
  The application consists of 6 different Microservices

  * offers-microservice-spring-boot - Spring Boot App with Offers data
  * shoes-microservice-spring-boot - Spring Boot App with Shoe data
  * wishlist-microservice-python - Python App with Wishlist data
  * cart-microservice-nodejs - Node.js App with Cart data
  * zuul-api-gateway - API gateway that proxies all the micro-services
  * ui-web-app-reactjs - Single Page Application that provides the UI
# Build docker images
  Build offers images
    
    cd offers-microservice-spring-boot
    docker build -t offers .
  Build shoes image
  
    cd shoes-microservice-spring-boot
    docker build -t shoes .
  Build wishlist image  
    
    cd wishlist-microservice-python
    docker build -t wishlist .
  Build cart image 
    
    cd cart-microservice-nodejs
    docker build -t cart .
  Build zuul-api image
    
    cd zuul-api-gateway
    docker build -t zuul-api .
  Build UI image
    
    cd ui-web-app-reactjs
    docker build -t ui .
# deploy application with container
    docker run --name offers -p 1001:1001 -d offers:latest
    docker run --name shoes -p 1002:1002 -d shoes:latest
    docker run --name wishlist -p 1003:1003 -d wishlist:latest
    docker run --name cart -p 1004:1004 -d cart:latest
    docker run --name zuul-api -p 9999:9999 -d zuul-api:latest
    docker run --name ui -p 8080:8080 -d ui:latest
# Open below port numbers in security groups
  1001,1002,1003,1004,9999,8080
# Check output in browser
  http://3.238.2.74:8080/
  
  ![image](https://user-images.githubusercontent.com/58024415/125563967-0e619b01-b5fc-472e-a2c6-3c5e53edee30.png)
