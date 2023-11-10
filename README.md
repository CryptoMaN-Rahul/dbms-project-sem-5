# dbmsproj
dbms project semester 5



1. **Creating Tables in phpMyAdmin:**

   First, let's create tables in phpMyAdmin. Follow these steps:

   - Open your web browser.
   - Type `http://localhost/phpmyadmin` in the address bar and press Enter.
   - Log in if prompted.
   - in the left hand side ,  click on 'NEW' and create database 'dir1'

   **Note:** Make sure your XAMPP server is running.

   - Click on the "SQL" tab.
   - Copy and paste the following SQL commands to create the tables into the SQL query box:

   ```sql
   -- Users Table
   CREATE TABLE users (
       user_id INT AUTO_INCREMENT PRIMARY KEY,
       username VARCHAR(255) NOT NULL,
       password VARCHAR(255) NOT NULL,
       email VARCHAR(255) NOT NULL
   );

   -- Items Table
   CREATE TABLE items (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(255) NOT NULL,
       description TEXT NOT NULL,
       price DECIMAL(10, 2) NOT NULL,
       image_url VARCHAR(255),
       category VARCHAR(255) NOT NULL,
       seller_id INT NOT NULL,
       contact_details TEXT,
       FOREIGN KEY (seller_id) REFERENCES users(user_id)
   );

   -- Messages Table
   CREATE TABLE messages (
       id INT AUTO_INCREMENT PRIMARY KEY,
       sender_id INT NOT NULL,
       receiver_id INT NOT NULL,
       message TEXT NOT NULL,
       sent_at DATETIME NOT NULL,
       FOREIGN KEY (sender_id) REFERENCES users(user_id),
       FOREIGN KEY (receiver_id) REFERENCES items(seller_id)
   );

   -- Watchlist Table
   CREATE TABLE watchlist (
       id INT AUTO_INCREMENT PRIMARY KEY,
       user_id INT NOT NULL,
       item_id INT NOT NULL,
       added_on DATETIME NOT NULL,
       FOREIGN KEY (user_id) REFERENCES users(user_id),
       FOREIGN KEY (item_id) REFERENCES items(id)
   );
   ```

   - Click the "Go" button to execute these SQL commands.

2. **Organizing Files in XAMPP (htdocs directory):**

   To create a folder and save your files in XAMPP's htdocs directory, follow these steps:

   - Open your file explorer.

   - Navigate to the XAMPP installation directory, e.g., `C:\xampp` or `/opt/lampp` on Linux.

   - Inside the XAMPP directory, locate the `htdocs` folder.

   - Create a new folder named `dbproj` inside the `htdocs` folder.
   - create a new folder name-> 'uploads' inside the 'dbproj' folder.


   - Save all your project files inside the `dbproj` folder.

   Your project files should now be accessible at `http://localhost/dbproj/`.


TO ACCESS TYPE - http://localhost/dbproj/Register1.php      -->  in your browser  , apache and phmyadmin should be running
