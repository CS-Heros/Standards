# Standards

This repo will contain the standard rules we should follow while building our graduation project.

---

### Project Structure.

- Mobile App
    - Built with flutter (Most likely, Will be discussed).
    - Use 'aysa' app for inspiration : https://apps.apple.com/us/app/aysa/id1357153511
- Backend
    - Restful api service
        - Built with laravel.
        - Deployed to shared hosting or AWS this doesn't matter.
        - Used for :
            - Connecting the mobile app with DL-Models using standard restful api.
            - Storing users info.
            - Manage diseases data.
            - Managing the dataset.
    - DL Models
        - Built with python & flask.
        - Deployed to AWS EC2 instances as microservices.
        - Uses one standard structure and code - only the model file will change.
        - Consider the possibility of using **one flask app** to serve all models instead of microservices approach.
        - Takes standard request & Replies with standard response.

---

### Important considerations.

- General
    - Commit messages are important
    - Restful api schemes will be set at first.
    - Clean code and architecture are mandatory.
- Mobile app
    - Preferred to build the app on MVVM arch.
    - Endpoints might change.
    - Response structure might change so abstract the models.
    - Handle errors locally ex:404 error will be sent without message, 200 code is the only valid response you will get.
    - Responses will be documented in this file or will be documented as postman documentation (link will be here).
    - Take localisation in consideration (API responses should be localised but you should send local key with every
      request ex:'ar')
- Laravel backend
    - Use PHP-8
    - DB-Scheme will be built with skipper.
    - Never change skipper generated files (Models & Migrations).
    - DB Scheme should be separated from restful api scheme.
    - Orchid will be used for building control panel.
    - Normal controllers will be used for serving restful api requests.
- Flask backend & DLS
    - Use virtual env so that we can update the app easily from GitHub.
    - OOP is important.
    - Return values should be keys not numbers.
    - Input and output scheme shouldn't change frequently.

---

### Response Examples

Will be written soon.