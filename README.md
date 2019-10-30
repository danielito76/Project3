# **Project 3: Date-A-Base** ![ga_cog_large_red_rgb](https://cloud.githubusercontent.com/assets/40461/8183776/469f976e-1432-11e5-8199-6ac91363302b.png)
## Dating Experience Website
# Team
- Daniele Nocito
- Adesola Oni-Shogbonyo
- Michael G. Laird
- Francisco Dias

## Overview
This is my third project from General Assembly's Software Engineering Immersive Course. It is a group project built in one week.
Date-a-Base is a virtual community where everyone can find and share advices about beautiful and funny locations in London and surroundings, suitable for a dating. The type of locations meet a wide range of preferences which can be filtered depending on the expectations.

- [DATE-@-BASE] (https://project3-date-a-base.herokuapp.com/#/)
- [Readme] (https://github.com/danielito76/Project3/blob/master/README.md)


![First GIF](/src/img/readme-screenshots/Date-A-Base-GIF1.gif)

![Second GIF](/src/img/readme-screenshots/Date-A-Base-GIF2.gif)


## Project Brief
​
### The following requirements were a must:
​
* **Build a full-stack application** by making your own backend and your own front-end
* **Use an Express API** to serve your data from a Mongo database
* **Consume your API with a separate front-end** built with React
* **Be a complete product** which most likely means multiple relationships and CRUD functionality for at least a couple of models
* **Implement thoughtful user stories/wireframes** that are significant enough to help you know which features are core MVP and which you can cut
* **Have a visually impressive design** to kick your portfolio up a notch and have something to wow future clients & employers. **ALLOW** time for this.
* **Be deployed online** so it's publicly accessible.
* **Have automated tests** for _at least_ one RESTful resource on the back-end. Improve your employability by demonstrating a good understanding of testing principals.
​
---
​
### The following deliverables were required:
​
* A **working app** hosted on the internet
* A **link to your hosted working app** in the URL section of your Github repo
* A **git repository hosted on Github**, with a link to your hosted project, and frequent commits dating back to the _very beginning_ of the project
* **A `readme.md` file** with:
    * An embedded screenshot of the app
    * Explanations of the **technologies** used
    * A couple paragraphs about the **general approach you took**
    * **Installation instructions** for any dependencies
    * Link to your **user stories/wireframes** – sketches of major views / interfaces in your application
    * Link to your **pitch deck/presentation** – documentation of your wireframes, user stories, and proposed architecture
    * Descriptions of any **unsolved problems** or **major hurdles** you had to overcome
​
## Project Execution
​
We spend the first day exploring ideas and throughly planning our project. This included:
* Wireframes


![Wireframe](/src/img/readme-screenshots/Date_A_Base_Wireframe.jpg)



* Trello board


![Trello board](/src/img/readme-screenshots/Date-A-Base-Trello.png)


* Allocation of responsibilities
* Decide back and frontend approach
​
Our daily routine involved a morning brief and an end of day summary.
​
​
### Technologies Used
* HTML5
* CSS3
* SASS
* JavaScript (ES6)
* Git
* GitHub
* External API
* React
  * React-mapbox-gl
  * React-select
  * React star-rating-component
  * React star-ratings
  * React- Toastify
* Webpack
* Bulma
* Node JS
* Babel
* Insomnia
* REACT
* Filestack-react
* Monogdb
* Nodemailer
* Express
* Heroku
* Google Fonts
​
​
## Approach Taken
### Navbar
Wanted logged in user avatar to display, involved storing the information in local storage, then retrieving the image url.
FileStack
Wanted a smooth, easy way for users to upload images, rather than having to post any pictures online manually before able to do so. Found filestack online and used the documentation + other examples on github to implement. Makes it much easier as our site relies heavily on use input.
### FIlters
As our site is about helping users make decisions, we wanted to make filters a big component - hence their placement on the landing page. Aside from using React-Select to format the filter dropdowns, the logic involved getting the data from the dropdowns, storing it in state, then passing this over to the locations index page so that it shows a pre-filtered list of locations. Else the user can go straight to the index page.
### Users
We wanted to create an index of user profiles, perhaps more useful in future iterations, but for the purpose of searching other like minded users. On this page we didn’t want the logged in user to see their own profile. This involved using a filter function before mapping over the users to display them.
As part of this, in order to find out more information about the user, we created a page asking for user details after the initial register. We did not make the extra questions required so that we could post the initial register, carry over the form details in state and then combine both form details to update the user.
We also wanted the user to be able to edit their own profile, which we allowed using a function to only show the edit button on a user own profile.
Styling
Based the style off of an old movie theatre style with neon effects. Used text shadow/box shadow to get a neon effect.
Wanted a transparent fixed top navbar, but also had wanted to use the fade in method on scroll for better UX. Found some guidance online and adapted to our needs.
Win
Enjoyed learning more about react, particularly storing things in state/local storage.
Implementing new technologies - filestack loder + react-select.
Blocker
Getting the navbar to stay at the bottom of the screen with no content, without hard coding viewport height as this caused problems on the locations index
### Contact format
We enabled the Contact Form to send email to a our specific gmail address from the backend.
### About Us
In the About Us page we used a 3d effect CSS to make the page more interesting
### Terms and Conditions
The same as About Us and Contacts, Terms and Conditions are in the footer so that accessible everywhere in the website. We decided to display the documentation using a Bulma modal overlay effect implemented with Javascript code.

![Home](/src/img/readme-screenshots/Date-A-Base-Home.png)

![Index](/src/img/readme-screenshots/Date-A-Base-Index.png)

![Show](/src/img/readme-screenshots/Date-A-Base-Show.png)

![Fullmap](/src/img/readme-screenshots/Date-A-Base-Fullmap.png)

![Add](/src/img/readme-screenshots/Date-A-Base-Add.png)

![Contact](/src/img/readme-screenshots/Date-A-Base-Contact.png)

![Modal](/src/img/readme-screenshots/Date-A-Base-Modal.png)



## Functionality

### Map Show

```javascript
<Map
  className="map"
  style="mapbox://styles/mapbox/streets-v9"
  zoom={zoom}
  center={[this.state.location.longitude, this.state.location.latitude]}
  containerStyle={{
    height: '100%',
    width: '100%'
  }}
>
  <Marker
    coordinates={[this.state.location.longitude, this.state.location.latitude]}
    anchor="bottom">
    <img width="30px" height="30px" src={mapMarker} />
  </Marker>
</Map>
```

### Rating
```javascript
{Auth.isAuthenticated() && <form onSubmit={this.handleSubmit}>
  <div className="field">
    <StarRatings
      name="rating"
      starRatedColor="#FFC300"
      numberOfStars={5}
      starDimension="15px"
      starSpacing="5px"
      changeRating={this.handleChangeRating}
      rating={this.state.formData.rating}
    />

  </div>
  <div className="field">
    <textarea
      name="content"
      className="textarea"
      placeholder="Add a comment..."
      onChange={this.handleChangeContent}
      value={this.state.formData.content}
    />
  </div>

  <button className="submiticon" ><FontAwesomeIcon className="icon" icon={faEnvelope} /></button>
</form>}
```

### Avatar in Navbar
```javascript
{Auth.isAuthenticated() && <div className="navbar-item avatar">
  <div className={`dropdown is-right ${this.state.dropdownOpen ? 'is-active' : ''}`}>
    <div className="dropdown-trigger">
      <button className="navIcon" aria-haspopup="true" aria-controls="dropdown-menu" onClick={this.toggleDropdown}>
        <span className="icon is-small">
          <img
            src={`${Auth.getUser().image}`}
            aria-hidden="true"
          />
        </span>
      </button>
    </div>
    <div className="dropdown-menu" id="dropdown-menu" role="menu">
      <div className="dropdown-content">
        <Link to={`/profiles/${Auth.getUser()._id}`} className="dropdown-item">
        My Profile
        </Link>
        <a className="dropdown-item"  onClick={this.logout}>
        Logout
        </a>
      </div>
```
### Filters
```javascript
componentDidMount() {
  axios.get('/api/locations')
    .then(res => {
      this.setState({ ...this.props.location.state, locations: res.data, filteredLocations: res.data})
    })
}
```
### Contact page
```javascript
const mailer = require('../lib/mailer')
const { USER } = require('../config/environment')

function emailRoute(req, res, next){
  const name = req.body.name
  const email = req.body.email
  const message = req.body.message
  const content = `name: ${name} \n email: ${email} \n message: ${message} `

  const mail = {
    from: name,
    to: USER,  //Change to email address that you want to receive messages on
    subject: 'New Message from Contact Form',
    text: content
  }

  mailer.sendMail(mail, (err) => {
    if (err) next(err)
    else res.json({ message: 'Message sent' })
  })
}

module.exports = {
  email: emailRoute
}
```
### Image uploader
```javascript
handleUploadImages(result) {
  const formData = {...this.state.formData, image: result.filesUploaded[0].url}
  this.setState({ formData })
}

<div className="field">
  <label className="label">Image</label>
  <ReactFilestack
    mode="transform"
    apikey={fileloaderKey}
    buttonText="Upload Photo"
    buttonClass="button"
    className="upload-image"
    options={options}
    onSuccess={(result) => this.handleUploadImages(result)}
    preload={true}
  />
  {this.state.formData.image && <img src={this.state.formData.image} />}
</div>
```
### Testing
```javascript
describe('POST /locations', () => {

  let token

  beforeEach(done => {
    User.create(testUser)
      .then(user => {
        token = jwt.sign({ sub: user._id }, secret, { expiresIn: '167h' })
        done()
      })
  })

  afterEach(done => {
    Location.remove({})
      .then(() => User.remove({}))
      .then(() => done())
  })


  it('should return a 401 response without a token', done => {
    api
      .post('/api/locations')
      .send(testData)
      .end((err, res) => {
        expect(res.status).to.eq(401)
        done()
      })
  })

  it('should return a 201 response with a token', done => {
    api
      .post('/api/locations')
      .set('Authorization', `Bearer ${token}`)
      .send(testData)
      .end((err, res) => {
        expect(res.status).to.eq(201)
        done()
      })
  })

  it('should return an object', done => {
    api
      .post('/api/locations')
      .set('Authorization', `Bearer ${token}`)
      .send(testData)
      .end((err, res) => {
        expect(res.body).to.be.an('object')
        done()
      })
  })

  it('should return the correct fields', done => {
    api
      .post('/api/locations')
      .set('Authorization', `Bearer ${token}`)
      .send(testData)
      .end((err, res) => {
        expect(res.body).to.contains.keys([
          '_id',
          'name',
          'addressLine1',
          'addressLine2',
          'addressCity',
          'addressPostCode',
          'longitude',
          'latitude',
          'actType',
          'cost',
          'dateNum',
          'desc',
          'image',
          'contactNumber',
          'link'
        ])
        done()
      })
  })

  it('should return the correct data', done => {
    api
      .post('/api/locations')
      .set('Authorization', `Bearer ${token}`)
      .send(testData)
      .end((err, res) => {
        expect(res.body.name).to.eq(testData.name)
        expect(res.body.addressLine1).to.eq(testData.addressLine1)
        expect(res.body.addressLine2).to.eq(testData.addressLine2)
        expect(res.body.addressCity).to.eq(testData.addressCity)
        expect(res.body.addressPostCode).to.eq(testData.addressPostCode)
        expect(res.body.cost).to.eq(testData.cost)
        expect(res.body.actType).to.deep.eq(testData.actType)
        expect(res.body.dateNum).to.deep.eq(testData.dateNum)
        expect(res.body.image).to.eq(testData.image)
        expect(res.body.contactNumber).to.eq(testData.contactNumber)
        expect(res.body.link).to.eq(testData.link)
        done()
      })
  })
})

```

### Wins, Blockers and key learnings

The most important win was definitely our capacity of working together as a team. Besides that must be mentioned some particular key features that we were able to build: the user profile; posts that can be commented, edited, liked or deleted by members; the map which shows a preview of each location; the different filters on the locations index; the possibility of assigning a rating to the locations; the function of uploading pictures; and finally the users can interact with founders via Contact form.
We had episodes of blockers when we were building the most complex functions that I just mentioned above, but we are particularly proud of being able to find the solutions and make them working.
The key learning for this project is definitely the team work: especially technically, as we had to handle the hole project managing different branches on GitHub; but also from a Human and organisational point of view. 




## Future content
* Address lookup function consuming a public API
* Enhancing functions and layout according to a User Experience research
* Improving the Graphics
