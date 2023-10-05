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

## To Run
```
cp .env.example .env
docker compose up
```
Using the example config, the data endspoints should be available on port `8080` and the UI on port `3000`.

## Dev
In `lumen-backend`:
```bash
composer install                     # Install dependencies
php artisan migrate:fresh            # Migrate
php -S 0.0.0.0:8080 public/index.php # Serve
```

In `vue-frontend`:
```bash
npm install # Install dependencies
npm run dev # Serve
```

## Personal Notes
* On the chart
  * Used `chart.js` as a base for the chart
  * Implementing highly customized charts is difficult
  * A quicker solution would've been to use an "out of the box" bar chart from the `chart.js` library
  * Extended and made a custom chart with a custom scale
  * Lots of drawing on canvas, wich is annoying when making something of variable width
* On the data
  * Was not provided a data structure to work with
  * Elected to use whole numbers in the database and then calculated percentages in the model
  * Database structure:
    ```
    happiness:
      - id
      - create_on
      - updated_on
      - name
      - is_workplace
      - very_happy
      - happy
      - content
      - unhappy
      - very_unhappy
    ```
  * A nullable one to many relation defining a parent "workplace" happiness may be useful