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
  * Implementing highly customized charts is difficult and time consuming
    * A quicker solution would've been to use an "out of the box" bar chart from the `chart.js` library, but that wouldn't fit the design I was given
    * Could have also maybe just drawn on a canvas and not made anything responsive, that seems less than ideal though.
  * Used `chart.js` as a base for the chart
  * Extended and made a custom chart with a custom scale
  * Lots of drawing on canvas, which is annoying when making something of variable width
* On the data
  * Was not provided a data structure to work with
  * Originally thought that "Workplace" should be an aggerate sum of all the other happiness values
    * Abandoned this after getting clarification that workplace values also needed the ability to be edited on their own—as an aggreagate editing woiuldn't be possible
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
  * A nullable one to many relation defining a parent "workplace" happiness may be useful, and maybe feel a bit cleaner :thinking:, but that would have me changing the lumen model, the controller, and the store
 in the frontend
* Things I like:
  * The lumen app looks great. Could probably stand to clean up some of the template files, but that's it.
  * While the spacing and some of the labels on the chart aren't *perfect*, it's still pretty close and it looks good. It's also responsive.
* Things I dislike:
  * The data structure feels *weird* and I'm not entirely sure how to fix it within the parameters I was given.
    * I don't like workplace being denoted via a boolean checkmark
  * The frontend is not completely responisive. On smaller screens elements will overlap. Was it one of the requirements? No. But it still annoys me.
  * I did not use a library like TailwindCSS. Admittedly the styling was minimal.
  * I only just picked up Vue, I'm sure there's cleaner ways to do things than what I did.
  * The types on the frontend—between the store and the chart at least—feel all over the place, could probably organize those better.
  * The code for the chart is a bit of a mess. I'm not thrilled about using a custom plugin to define column gradients.