# Art Generator Project
This is the GitHub Pages Site for CSCI 2340: Software Engineering, Art Generator Project at Brown University. <br />
**Members**: Malique Bodie, David Doan, Alina Kim, Gus LeTourneau, Yingjia Liu, Alexander Pratt, Morgann Thain, Haiyang Wang <br />
**Semester**: Spring 2024 <br />
**Current Project Repository:** [Art Generator Repository](https://github.com/newalina/art-gen)<br />
**Contact for Feedback:** alina_kim@brown.edu


## Overall Product Description
The Art Generator Project is a user-driven, web-based art generation product that provides its user with modified images and videos using real-time data centered around social causes. Users can provide input of live camera input or generic stock photos, which will be modified depending upon data relating to climate change including rising temperatures, ice melting, deforestation, rising sea levels, and wildlife exctinctions. Users will be able to share their new art creations by file download or through social media. This project places an emphasis on security and privacy for user data that is used in the application.

## Product Specifications
* The interface will support a share button that allows the user to specify the desired output format ie. gif, image, or short video, as well as a destination that includes social media sites and a local download option. <br />
* The web application will take user web cam data as input and generate various stylized, data-specific outputs. The generated output will be a creative representation of environmental data, using color, motion, and intensity to represent various trends in the data. <br />
* The user will have the ability to choose from multiple environmental datasets including global temperature, water level, precipitation rates, etc… which will each generate different data-specific outputs that reflect creative renderings of the environmental data trends. <br />
* The main user interface will be a web application that takes user inputs through user panel and generate outputs(image/ gif/ video) accordingly. <br />
* The interface will generate texts explaining how we generate the outputs(which dataset is employed) and the meaning behind them(what’s the environmental or social impact) base on user’s dataset choice. <br />
* The interface will include a user panel such that the user can adjust parameters or choosing between datasets to generate specific output they desire. <br />

## High-Level System Architecture

![Overall System HLD](/img/arch_Overall.jpg)

#### System User
**Description:** The System User component is the end-user that is using the Art Generator Project Application. The intent is for this user to control elements such as source graphics, datasets, and output options for the graphics generation. <br/>

#### Front End Driver
**Description:** The Front End Driver comprises the entirety of the Front End operation. This driver interacts with the System User via the User Interface and interacts with the Back End via the Front End / Back End Gateway. This driver acts as a functionality to handle user input, process the input, send the input to the Back End, and output the result of the System User's command. This section will be covered in more detail in the "Front End Driver Architecture" section. <br/>

#### Back End Driver
**Description:** The Back End Driver comprises the entirety of the Back End operation. This driver interacts with the Front End via the Front End / Back End Gateway and with external APIs via External API Access. The Back End Driver is where the heavy duty computation relevant to the Art Generation Project takes place. This section handles messages sent from the back end and returns an image or video stream to the front end to be output to the System User. The image processing itself is affected both by internal modules and by external API that provide data. This section will be covered in more detail in the "Back End Driver Architecture" section. <br/>

#### User Interface
**Description:** The User Interface is a gateway between the System User and the Front End. It is through the User Interface that the System User may choose image sources, choose datasets to be used, and select how they would like their creation to be output. The Front End Driver handles the User Interface activity by sending updated messages to the Back End Driver for processing. <br/>

#### Front End - Back End Gateway
**Description:** The Front End - Back End Gateway is the gateway between the Front End Driver and Back End Driver of the Art Generation Project. This gateway is essentially the space in which messages are sent between the Front End Driver and Back End Driver to provide data to either module. <br/>

#### External API Access
**Description:** The External API Access represents the Back End Driver using external API for two purpsoes. The first purpose is to gather data from organizations like NASA, NOAA, EPA, UN, etc, that can be used to drive the art generation portion of this project. The second purpose is to use external API from social media sites like Snapchat, Facebook, Instagram, and X, so that the System User can directly upload their images to be shared across the internet. 

#### Social Cause Data
**Description:** As mentioned in the "External API Access" section, Social Cause Data represents the data that is gathered from organizations (NASA, NOAA, EPA, UN, etc.) that is used to drive the art generation portion of the project. 

#### Social Media Connectivity
**Description:** As mentioned in the "External API Access" section, Social Media Connectivity represents the API used to share the generated art to social media sites such as Snapchat, Facebook, Instagram, and X. 

#### Logging and Error Checking
**Description:** This is not mentioned on any diagram, however, Logging and Error Checking is vital to this project. Each individual subsystem will utilize shared logging and error checking methods to improve the developer's ability to debug and develop the software for this project. It should be assumed that all subsystems in this section or future sections (Front End Driver Architecutre and Back End Driver Architecture) will utilize the shared Logging and Error Checking components. Note, since there are a variety of languages being used for development, each language will have its own logging and error checking library. The goal will be to make the outputs of each type similar so that debugging will become uniform.   



## Front End Driver Architecture

![Front End HLD](/img/arch_FrontEnd.jpg)


#### User Command
As described in the 'High-Level System Architecture' Section, the System User is ...
Features include: Mouse, keyboard, and Camera Detection <br />
Security: Safe camera access <br />
Technology: TSX <br />

Generate, Import Personal Data Set, Select Mode (Camera, Image, Video, etc), Select Effects or Data Set to be Used, Login, Download File, Export File to Social Media





#### System Response
Acts as a central connection between the user and the processes. Displays output to the user component. <br />
Features include: User Panel, Dataset Selection, Parameter Customization, Animations, <br />
Technology: NextJS, p5.js, three.js, canvas.js <br />

## Back-End Architecture

![Back End HLD](/img/arch_BackEnd.jpg)

#### Back End Command Interface
Combines user requests with real time data from external API to affect image processing. <br />
Technologies: Python, OpenCV <br />

#### Database
Way of accessing external data relevant to user input selections <br />
Technologies: Python <br />

#### Art Generation Driver
Stores recent data for faster computations. <br />
Technologies: SQL <br />



## Team Member Expected Assignments
We have divided our team into three sub-teams to tackle the challenging problems associated with creating a web-based application that is driven by computer vision and image processing. The three sub-teams are: Front End, Back End, and Graphics. Each team covers certain aspects of the code base, that collectively form the entirety of the Art Generation Project.

**Malique Bodie:**      Graphics - ENTER ROLE HERE<br />
**David Doan:**         Graphics - ENTER ROLE HERE <br />
**Alina Kim:**          Front End, Project Lead - ENTER ROLE HERE <br />
**Gus LeTourneau:**     Graphics - ENTER ROLE HERE <br />
**Yingjia Liu:**        Front End - ENTER ROLE HERE  <br />
**Alexander Pratt:**    Back End - ENTER ROLE HERE <br />
**Morgann Thain:**      Back End - ENTER ROLE HERE <br />
**Haiyang Wang:**       Graphics - ENTER ROLE HERE <br />
