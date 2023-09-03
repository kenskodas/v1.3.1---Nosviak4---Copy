# Nosviak4

Firstly, we would like to express our gratitude for your purchase of Nosviak4. Your support is deeply valued. This iteration marks the latest advancement in the Nosviak product line, encompassing several sought-after next-generation features desired by today's discerning customers.

## Sales pitch

Unveiling **Nosviak4**: the CNC innovation pinnacle. It's not just advanced and secure – it's a revolution in user experience. With state-of-the-art **ARGON2ID** security, your data defies breaches. Nosviak4 excels under pressure, adding just 0.1% CPU load for two active admins and 0.8% for ten users. Seamlessly meld your user experience using **SQLite** and **MySQL**. Elevate your CNC involvement – it's **Nosviak4** time.

## Requirements & Installation

Nosviak4's recommended server specifications

- `CPU: 4 cores at 3.0GHz`
- `RAM: 8GB DDR4`

Installing Nosviak4 is a straightforward process, made easier by its departure from the default use of MySQL and not defaulting SQLite

Prior to any action, upload your `*.ecl` file and relocate/place it to the `./assets/` directory. Failing to do so will render the CNC inoperative until the task is completed.

1. Upload your files to your VPS, for the best user experience make sure your server reaches the recommended specifications for Nosviak4.
2. After uploading your files, the next step involves granting execution permission by executing the command

   ```bash
   chmod +x Nosviak4
   ```

3. It's time to install screen to enable running Nosviak4 as a background process.
   - Ubuntu/Debian

     ```bash
     sudo apt install screen
     ```

   - Centos/RedHat/RHEL

     ```bash
     yum install screen
     ```

4. Great! Now it's time to run your Nosviak4 binary, and you can achieve this by using the following command.

   ```bash
   screen -S nosviak4 -dm ./Nosviak4`
   ```

Fantastic job! You've effectively installed Nosviak4. If you're interested in delving further into Nosviak4 and discovering how to monetize it for your unique application, take a deep dive into this directory. Inside, you'll uncover tailored information just for you. And should you have any additional inquiries, feel free to reach out to us through FB or contact Harry.

[NEXT-STEP] After completing this tutorial, I urge you to consider delving into the BRANDING.MD file for further insights.
