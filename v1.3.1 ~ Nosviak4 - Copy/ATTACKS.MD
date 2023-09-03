# Attacks

This document serves as a guide to initiate the process of integrating your methods into Nosviak4. It's crucial to understand that there are two distinct approaches for adding your methods. The first method involves utilizing the ./assets/attacks/apis.json file, while the second method entails utilizing the web dashboard.

## Web dashboard

Please be aware that this method will only work on versions higher than `v1.3.1`

Kindly be aware that in order for the web dashboard to open without any issues, you should access the ./assets/web.toml file. Within this file, please verify that the enabled field is set to true and that the address field is either left empty or contains your server's IP address.

1. Accessing the Web dashboard is a breeze. You can connect to it using any web browser. Simply type in this URL: `http://<SERVER>:3000/login`. To make it work, remember to replace `<SERVER>` with your server's actual IP address. Once you've reached this page you will be promoted to login to your account, make sure this account is **superuser**.

2. As a default setup, you'll notice a navigation bar positioned at the top of your page. Within this navbar, there's a dropdown labeled `attacks`. Click on this dropdown and proceed to select `APIs`.

3. Upon landing on the page, you'll encounter text that reads `API Methods`. If you don't see this text, it indicates that you haven't completed the setup accurately. give it another shot or contact support. When the API Methods text comes into view, you'll notice a button situated beneath it, labeled Add New API Method. By clicking on this button, an offcanvas will emerge, presenting you with input fields to create your inaugural method effortlessly!

Feel free to repeat this process as many times as you'd like to generate methods without any limitations, it's your CNC do as you wish!

## `./assets/attacks/apis.json`

We highly advise utilizing the *web dashboard* for adding methods; however, if you're well-versed in JSON, you're welcome to employ the `./assets/attacks/apis.json` approach.
