# AWP Sample Project
This project should give you a good representation of what we do here at Amazing Workplace. Please create a web application based on the Figma file design using Vue.js for the front-end and Lumen for the back-end. It should be containerized using Docker and hosted in a private GitHub repository.

## Details
1. Private GitHub Repository:
 * Create a private GitHub repository for this project.
 * Share access with the hiring team.
2. Containerization:
 * Containerize the Vue.js front-end and Lumen back-end using Docker.
 * Include a docker-compose.yml file for easy deployment and scaling.
3. Vue.js Front-End:
 * Create a new Vue.js project.
 * Implement a user-friendly and interactive user interface based on the provided design.
 * Use Vue.js best practices and state management (e.g., Pinia) where necessary.
4. Lumen Back-End:
 * Create a Lumen back-end application.
 * Implement read and write APIs that interact with a database.
 * Implement at least basic data validation and error handling (e.g., ensure numbers from
inputs).
5. Authentication:
 * None. There is no need for login/auth for this application so don’t worry about it.
6. Database:
 * Use a SQL-based database system (e.g., MariaDB) to store data for the back-end.
 * Design the database schema (e.g., a single table) to support the required functionality.
7. Deployment:
 * Include instructions for deploying the project locally using Docker and any required
environment variables.

## My Notes
* Backend
  * Employee happiness data is in percentages by department/team



# NOTES
* Vue/Lumen starter project with split between front and back
  * https://github.com/gentritabazi/vue-lumen-starter/tree/master
* Vite Lumen starter
  * https://github.com/bcakmakoglu/vite-lumen-starter/blob/develop/app/Providers/Vite/Vite.php
* Vue/Docker/Nginx (members only story)
  * https://medium.com/bb-tutorials-and-thoughts/how-to-serve-vue-js-application-with-nginx-and-docker-d8a872a02ea8
* https://dev.to/nas5w/how-to-serve-a-vue-app-with-nginx-in-docker-4p54
* Vue + Vite Micro Frontend
  * https://medium.com/@fonsecalovitor/micro-frontend-with-vue-vite-83276848314c

* This looks pretty much what I need to be doing
  * Seperate Lumen and Vue, Docker
  * https://medium.com/remote-worker-indonesia/developing-docker-multiservices-application-using-git-submodule-7bf9ed724004

* Use `docker-compose up --build` to launch

* https://stackoverflow.com/questions/74950533/how-to-import-index-vue-files-without-specifying-the-file-name-using-vue-3-and-v Import index.vue files