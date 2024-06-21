# Table of Contents
- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [Installation](#installation)
  - [Standalone](#standalone)
    - [Requirements](#requirements)
      - [Java Development Kit](#java-development-kit)
      - [The Server Application Bundle](#the-server-application-bundle)
    - [Running the Server](#running-the-server)
  - [Deploying on an Existing Application Server](#deploying-on-an-existing-application-server)
  - [Docker](#docker)
    - [Pulling the Image](#pulling-the-image)
    - [Deployment](#deployment)
      - [Starting the Container](#starting-the-container)
      - [Using a Custom Database](#using-a-custom-database)
      - [Additional Information](#additional-information)
    - [Generate Your Own Image](#generate-your-own-image)
- [Appendix A. Securing the Server](#appendix-a-securing-the-server)
  - [Recommendations](#recommendations)
- [Appendix B. Starting the Server on Boot](#appendix-b-starting-the-server-on-boot)
- [Appendix C. Using a Reverse Proxy](#appendix-c-using-a-reverse-proxy)
- [Appendix D. Accessing the Database](#appendix-d-accessing-the-database)


# Appendix A. Securing the Server
## Recommendations
* Make sure the user running the server only has access to the data directories and has as little other privileges as possible. Also, disable its shell access as instructed in the [installation section](#installation).
* Install a firewall (ufw works pretty well) and restrict access to non-necessary ports.
* Disable SSH user/password authentication and favor key-based authentication.
# Appendix B. Starting the Server on Boot
# Appendix C. Using a Reverse Proxy
# Appendix D. Accessing the Database
