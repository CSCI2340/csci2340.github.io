# Art Generator Project

This is the GitHub Pages Site for CSCI 2340: Software Engineering, Art Generator Project at Brown University. <br />
**Members**: Malique Bodie, David Doan, Alina Kim, Gus LeTourneau, Yingjia Liu, Alexander Pratt, Morgann Thain, Haiyang Wang <br />
**Semester**: Spring 2024 <br />
**Current Project Repository:** [Art Generator Repository](https://github.com/newalina/art-gen)<br />
**Contact for Feedback:** alina_kim@brown.edu

## Overall Product Description

The Art Generator Project is a user-driven, web-based art generation product that provides its user with modified images and videos using real-time data centered around social causes. Users can provide input of live camera input or generic stock photos, which will be modified depending upon data relating to climate change including rising temperatures, ice melting, deforestation, rising sea levels, and wildlife exctinctions. Users will be able to share their new art creations by file download or through social media. This project places an emphasis on security and privacy for user data that is used in the application.

## Product Specifications

- The interface will support a share button that allows the user to specify the desired output format ie. gif, image, or short video, as well as a destination that includes social media sites and a local download option. <br />
- The web application will take user web cam data as input and generate various stylized, data-specific outputs. The generated output will be a creative representation of environmental data, using color, motion, and intensity to represent various trends in the data. <br />
- The user will have the ability to choose from multiple environmental datasets including global temperature, water level, precipitation rates, etc… which will each generate different data-specific outputs that reflect creative renderings of the environmental data trends. <br />
- The main user interface will be a web application that takes user inputs through user panel and generate outputs(image/ gif/ video) accordingly. <br />
- The interface will generate texts explaining how we generate the outputs(which dataset is employed) and the meaning behind them(what’s the environmental or social impact) base on user’s dataset choice. <br />
- The interface will include a user panel such that the user can adjust parameters or choosing between datasets to generate specific output they desire. <br />

## High-Level System Architecture

![Overall System HLD](/img/arch_overall.jpg)

#### System User

**Description:** The System User component is the end-user that is using the Art Generator Project Application. The intent is for this user to control elements such as source graphics, datasets, and output options for the graphics generation. <br/>

#### Frontend Driver

**Description:** The Frontend Driver comprises the entirety of the Frontend operation. This driver interacts with the System User via the User Interface and interacts with the Backend via the Frontend-Backend Gateway. This driver acts as a functionality to handle user input, process the input, send the input to the Backend, and output the result of the System User's command. This section will be covered in more detail in the "Frontend Driver Architecture" section. <br/>

#### Backend Driver

**Description:** The Backend Driver comprises the entirety of the Backend operation. This driver interacts with the Frontend via the Frontend-Backend Gateway and with external APIs via External API Access. The Back End Driver is where the heavy duty computation relevant to the Art Generation Project takes place. This section handles messages sent from the backend and returns an image or video stream to the frontend to be output to the System User. The image processing itself is affected both by internal modules and by external API that provide data. This section will be covered in more detail in the "Backend Driver Architecture" section. <br/>

#### User Interface

**Description:** The User Interface is a gateway between the System User and the Frontend. It is through the User Interface that the System User may choose image sources, choose datasets to be used, and select how they would like their creation to be output. The Frontend Driver handles the User Interface activity by sending updated messages to the Backend Driver for processing. <br/>

#### Frontend-Backend Gateway

**Description:** The Frontend-Backend Gateway is the gateway between the Frontend Driver and Backend Driver of the Art Generation Project. This gateway is essentially the space in which messages are sent between the Frontend Driver and Backend Driver to provide data to either module. <br/>

#### External API Access

**Description:** The External API Access represents the Backend Driver using external API for two purpsoes. The first purpose is to gather data from organizations like NASA, NOAA, EPA, UN, etc, that can be used to drive the art generation portion of this project. The second purpose is to use external API from social media sites like Snapchat, Facebook, Instagram, and X, so that the System User can directly upload their images to be shared across the internet. <br/>

#### Social Cause Data

**Description:** As mentioned in the "External API Access" section, Social Cause Data represents the data that is gathered from organizations (NASA, NOAA, EPA, UN, etc.) that is used to drive the art generation portion of the project. <br/>

#### Social Media Connectivity

**Description:** As mentioned in the "External API Access" section, Social Media Connectivity represents the API used to share the generated art to social media sites such as Snapchat, Facebook, Instagram, and X. <br/>

#### Logging and Error Checking

**Description:** This is not mentioned on any diagram, however, Logging and Error Checking is vital to this project. Each individual subsystem will utilize shared logging and error checking methods to improve the developer's ability to debug and develop the software for this project. It should be assumed that all subsystems in this section or future sections (Frontend Driver Architecutre and Backend Driver Architecture) will utilize the shared Logging and Error Checking components. Note, since there are a variety of languages being used for development, each language will have its own logging and error checking library. The goal will be to make the outputs of each type similar so that debugging will become uniform. <br/>

## Frontend Driver Architecture

![Frontend HLD](/img/arch_frontend.jpg)

#### User Command

**Description:** As described in the 'High-Level System Architecture' Section, the System User controls all aspects of the application through the User Interface. The purpose of the User Command sub-system is to convert the System User's commands in the User Interface to messages that can be sent across the Frontend-Backend Gateway into the Backend Driver. These commands can cover a wide range of options, which will be listed and described below: <br/>

- **Select Image Mode:** This type of command handles the System User selecting the input type into the art generation. Potential options include a live webcam image, a live webcam video, an image file, or a video file. <br/>
- **Select Image Source:** Different from the "Select Image Mode" option, this type of command refers to the actual sending of data relevant to the file type that is referred to in Select Image Mode. <br/>
- **Select Effects:** This type of command handles the System User selecting the effect type that they would like to be applied to the art generation. Potential options include a flame, drowning effects, or a drying effect. <br/>
- **Select Data Set:** This type of command handles the System User selecting the type of data set that they would like to use to generate their art. Options will include a variety of options from organzations like NASA, NOAA, EPA, and the UN. <br/>
- **Import Data Set:** This type of command handles the System User selecting an option to import their own data sets to be used for art generation. The System User can upload up to 3 different personal datasets to be stored if they have a user account. Similarly, the user will have access to any other public data set that is created by other users. <br/>
- **Generate:** This type of command allows the System user to generate their art, once all of the appropriate parameters such as image source and effect type have been chosen. <br/>
- **Download File:** This type of command allows the System User to download the file of the image or video that they have generated. <br/>
- **Export File:** This type of command allows the System User to export the image or video that has been generated to an external social media platform. <br/>
- **Login:** This type of command allows the System User to login to their user account. This enables the user to utilize their own personal data sets and have access to public datasets that are created by other users.<br/>

#### System Response

**Description:** The System Response subsystem is responsible for providing the System User with all data that drives the User Interface. Examples of this are datum coming from the backend relevant to the art generation such as the image data iteself. The System Response subsystem ensures that all outputs that should be expected from the System User input's are delivered from the Backend Driver. <br/>

## Backend Driver Architecture

![Backend HLD](/img/arch_backend.jpg)

#### Backend Command Interface

**Description:** The Backend Command Interface is the lifeblood of the Backend Driver. A high level description of the purpose of the Backend Command Interface is to handle input messages from the Front End Driver through the Frontend-Backend Gateway, perform some processing, and output the results of the input message, either to the Frontend or to an external API. In reality, the Backend Command Interface acts as a mediator for all computation. Once a message is received by the Backend Command Interface, it is the sole driver of accessing the proper API and Database's, and performing the art generation. It coordinates the data transfer to and from each subsystem and API, and is responsible for combining the cumulative efforts of each subsystem and outputting their result to the desired destination. <br/>

#### Database

**Description:** The Database holds relevant long term information that can be used by the system. This includes login information, uploaded datasets for each user, and saved images or videos for each user. The data from the Database can be accessed and used by any component in the Backend Driver, and should be treated securely as it will contain information relevant to any System User with a user account. <br/>

#### Art Generation Driver

**Description:** The Art Generation Driver is the most critical component to this project. Simply put, the Art Generation Project is a Image Signal Processing (ISP), Computer Vision (CV), Machine Learning (ML), and Deep Learning (DL) product. While there are critical components outside of the Art Generation, they are rendered useless unless we have quality graphics being generated. This subsystem drives all of the ISP needed for our project using technologies founded in CV, ML, and DL. The Art Generation Driver takes commands and data that are provided from the Backend Command Interface, and outputs its result to the Backend Command Interface. <br/>

## Team Member Expected Assignments

We have divided our team into three sub-teams to tackle the challenging problems associated with creating a web-based application that is driven by computer vision and image processing. The three sub-teams are: Frontend, Backend, and Processing. Each team covers certain aspects of the code base, that collectively form the entirety of the Art Generation Project. <br/>

**Malique Bodie:** Backend - User Authentication <br />
**David Doan:** Processing - Websockets <br />
**Alina Kim:** Project Lead, Frontend - Design and Development <br />
**Gus LeTourneau:** Processing - Data Processing <br />
**Yingjia Liu:** Frontend - Web Interface <br />
**Alexander Pratt:** Processing - Image Processing <br />
**Morgann Thain:** Backend - SQL Database <br />
**Haiyang Wang:** Processing - API Connections <br />
