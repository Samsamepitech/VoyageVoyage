# ecp
# ![image](https://user-images.githubusercontent.com/98088041/211883146-0163161d-c75b-44e9-9f8d-b584f066c4d6.png)


# Voyage Voyage - End Project 3 weeks - Coding Academy by Epitech
### Samira TAIBI- Vladimira GROSJEAN - Fanny THIBERT
=> A website like "TripAdvisor" 

# I - Dev part

## Create backend :

### Using expressjs/nodejs :

    mkdir API_voyages
    cd API_voyages
    npm init -y
    npm install express

### Create folders and file for API routes :

    mkdir routes
    cd routes
    touch files.js...
  
    mkdir config
    cd config
    touch db.js => enter parameters to acces to the database
![image](https://user-images.githubusercontent.com/98088041/211883388-348c5725-2a14-4150-b4d7-beddcc83f571.png)


### Install dependencies :

      npm i nodemon
      npm i axios
      npm i bcrypt
      npm i body-parser
      npm i cookie-parser
      npm i cors
      npm i crypto-js
      npm i debug
      npm i dotenv
      npm i express
      npm i fs
      npm i http-errors
      npm i jsonwebtoken
      npm i morgan
      npm i multer
      npm i mysql
      npm i nodemailer
      npm i pug
      npm i swagger-jsdoc
      npm i swagger-ui-express
  
    => do the same for all APIs
### tests with mocha chai

        npm install --save mocha chai
        mkdir test
        touch 'files-test'.js...
        npm run test
    
### Using mysql :

        sudo /etc/init.d/mysql start
        sudo mysql
        > CREATE DATABASE voyage
        > USE voyage
        > CREATE TABLES...
        
  use db [world](https://sql.sh/514-liste-pays-csv-xml) for countries and cities 
        
 ### UML Diagram :
![image](https://user-images.githubusercontent.com/98088041/211883453-07fa2eee-b430-47e0-832d-7e4bf947c89d.png)

        
### API documentation :

  * [swagger](http://localhost:3020/api-docs/#/)


![image](https://user-images.githubusercontent.com/98088041/211883527-de2db232-a1f8-4ae0-a4a2-cacc99a9e8bc.png)


### API Tripadvisor
        
 use [Tripadvisor](https://www.tripadvisorsupport.com/fr-FR/hc/owner/articles/517) API 

        mkdir TripAdvisor_API
        cd TripAdvisor_API
        npm init -y
        npm install express 
        
        mkdir routes
        cd routes
        touch files.js...
        ![image](https://user-images.githubusercontent.com/98088041/211883584-94da3133-eb05-4062-8e83-965f0e334b6d.png)

  
## Create frontend :
### Create a vue.js app :

      npm install -g @vue/cli
      vue create front-v
      => select your options

      cd front-v
      npm install
      npm run serve
      
### Install dependencies :

      npm i bootstrap
      npm i bootstrap-vue
      npm i ol
      npm i mdb-vue-ui-kit
      npm i parcel
      npm i pug
      npm i register-service-worker
      npm i vue
      npm i vue-axios
      npm i vue-router
      npm i vue3-openlayers
      npm i vuex
      npm install -S @fawmi/vue-google-maps
      
 ### Create folders and files for the front :
 
        mkdir 'folders'...components/views/router...
        touch 'files'...
   ![image](https://user-images.githubusercontent.com/98088041/211883628-fd8a1b3d-b72a-4443-881d-8f172e97758c.png)

   
   To manage uploading photos : use an image download website : [ImgBB](https://fr.imgbb.com/)
   
 # II - User part
 
 ## Plan of the website 
 
 ### User and Curator access :
 
 ![image](https://user-images.githubusercontent.com/98088041/211883698-00dbaa01-0802-428d-9c23-71d27bcfdab8.png)

 
 ### Admin access :
             
![image](https://user-images.githubusercontent.com/98088041/211883735-e10b4d7f-f180-4f67-8666-ada469cc976f.png)

 Home page
![image](https://user-images.githubusercontent.com/98088041/211883797-dccf197c-a85a-4ee6-a386-91685660ff65.png)

Login/register

![image](https://user-images.githubusercontent.com/98088041/211883877-34c2e459-249c-49c9-a0b7-c353c6299956.png)


Mailtrap 

![image](https://user-images.githubusercontent.com/98088041/211883963-f8d9d1e2-ffcf-44e1-99ef-48c1e4f32f95.png)


Profile page 

![image](https://user-images.githubusercontent.com/98088041/211884184-6a7e36ad-3d7b-4173-9a27-f5f6bc08e0d1.png)


All activities

![image](https://user-images.githubusercontent.com/98088041/211884241-dd9ed805-98aa-4d9f-b880-43061b4c9a45.png)

Most liked activities 

![image](https://user-images.githubusercontent.com/98088041/211884351-01788cdb-2574-46bf-bc0f-4a9496b3ee06.png)


