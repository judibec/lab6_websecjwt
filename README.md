# lab6_websecjwt

## Arquitectura
![image](https://github.com/user-attachments/assets/d36fc93a-a4fd-408e-a5f7-3a6609cd2168)

Vemos que se crea un amplify en donde se enlaza con github para implementar todos los archivos estaticos y cada vez que se despliegue algo nuevo el link del amplify se actualice y suba los cambios nuevos, esto es algo que consumira el usuario desde el browser

Por otro lado tenemos el servicio de cognito, donde configuramos las credenciales en el js config, esto nos permite tener seguridad en el sistema, cognito nos genera un jwt valido para validar la autenticacion

Por ultimo es el llamado o la comunicacion, tenemos una base de datos en dynamo donde guardamos la creacion de usuarios y los datos de latitud y longitud, es llamada mediante una lambda que tiene todo el backend y por ultimo disponibilizamos esta API mediante un apigateway, activamos todo el tema de CORS y habilitamos la cabecera de Authorization enlazandola con el cognito que creamos, asi se valida el jwt para dejarnos continuar con el flujo de la app

## Explicacion
Nos basamos en el tutorial que presenta aws para el uso de cognito en las aplicaciones https://aws.amazon.com/es/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/

## Evidencias

creacion del amplify
![image](https://github.com/user-attachments/assets/5b496f36-5d53-4846-ba8f-147c3799c52a)

la pagina se despliega correctamente
![image](https://github.com/user-attachments/assets/104e22b8-59f5-4c8d-b2c6-b7c87996b02c)

configuramos el cognito y recibimos un correo con un OTP para poder validarlo en la app
![image](https://github.com/user-attachments/assets/ab0ec644-1a30-47f0-ac3c-d78aa5269793)

Creamos el Backend, la lambda y la tabla en dynamo
![image](https://github.com/user-attachments/assets/ce80e98d-ec8f-4558-869c-d372ddf87468)
![image](https://github.com/user-attachments/assets/7bb66268-c8f5-4f45-b78a-dc203966a21d)

Creamos un ApiGateway y creamos un autorizador y realizamos la prueba
![image](https://github.com/user-attachments/assets/66f5f62a-482c-4a0d-be4a-713d9637d84b)
![image](https://github.com/user-attachments/assets/0bc8f7d6-079f-4856-b9ed-570fc65a6fd5)

Creamos un metodo POST, debemos tener los CORS activados
![image](https://github.com/user-attachments/assets/7f892a6c-a08b-48a8-85d4-4d63503c38a2)

Desplegamos en una etapa productiva
![image](https://github.com/user-attachments/assets/3309d8ff-5e63-4155-99e3-58bd3788a928)

Realizamos la prueba para llamar a un unicornio a alguna ubicacion en el mapa
![image](https://github.com/user-attachments/assets/2cb4f27d-8e7e-4b39-ab9d-5c296910bb16)
