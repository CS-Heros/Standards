# Standards

This repo will contain the standard rules we should follow while building our graduation project.

---

### Important Links

- [Drive](https://drive.google.com/drive/folders/1xJETdLUyRsgOnjRMnQou9g3Lu7s-DvwZ?usp=sharing)
- [Trello](https://trello.com/b/LQgGQhio/fcis-graduation-project-%F0%9F%94%A5)

### Team Members

- QA/QC Team
    - [Mahmoud Abas](https://github.com/mmabas77)
    - [Mohamed Badr](https://github.com/Mohamed-b2dr)
- Android Team
    - [Mahmoud Zewain](https://github.com/Zewain-tech)
    - [Omar Adel](https://github.com/omarzer0)
- Backend (Laravel) Team
    - [Mahmoud Mohamed Ramadan](https://github.com/mahmoudmohamedramadan)
    - [Ayda Mohammed](https://github.com/Ayda-mohammed)
- Deployment Backend Team
    - [Abdelrahman Khaled](https://github.com/Abdelrahman-Kh-Fouad)
    - Abdullah Mohamed
- UI/UX Team
    - [Mohamed Elazap](https://github.com/jrazap)
    - [Ghada Talaat](https://github.com/Ghada-Talaat)

---

### Project Structure

- Mobile App
    - Built with flutter (Most likely, Will be discussed).
    - Use '[aysa](https://apps.apple.com/us/app/aysa/id1357153511)' app for inspiration
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

### API Reference

- Reference : [JSON API Examples](https://jsonapi.org/examples/)
- General Scheme example
  `{ "status": "success",
  "data": [{...},...],
  "included": [{...},...],
  "errors": null }`
- Rules
    - Use versioning e.g. `url/api/v1/endpoint`
    - Specify language in the header e.g. `accept-language:ar` default is `en`
    - Specify generic status in the root of the json response
        - e.g. `"status": "success"`
            - errors are set to null
        - e.g. `"status": "failed"`
            - will be used when request can't be completed but errors are not specified
            - data,included and errors are set to null
        - e.g. `"status": "errors"`
            - data and included are set to null
    - Naming
        - Reference : [Resource Naming](https://restfulapi.net/resource-naming/)
        - Use these words as keys (For uniform usage)
            - name (e.g. a disease has a 'name' not a 'title')
            - title (e.g. an article has a 'title' not a 'name')
            - url
            - image (As json object not a link e.g. `"image":{url: "url-here",...}`)

**Any suggestions ? Just edit and make PR...**

- Postman Documentation Links
    - [Laravel App](/#)
    - [Flask App](/#)