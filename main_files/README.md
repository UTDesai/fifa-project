# FIFA 2026 Registration Portal (LAMP stack)

Basic registration portal using PHP & MySQL.

## Setup

1. **Create database and user (MariaDB/MySQL):**
    ```sql
    CREATE DATABASE fifa2026;
    CREATE USER 'reguser'@'localhost' IDENTIFIED BY 'yourpassword';
    GRANT ALL PRIVILEGES ON fifa2026.* TO 'reguser'@'localhost';
    FLUSH PRIVILEGES;
    ```

2. **Create table:**
    ```sql
    USE fifa2026;
    CREATE TABLE users (
        id INT AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(100) NOT NULL,
        email VARCHAR(100) NOT NULL,
        password VARCHAR(255) NOT NULL,
        registered_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );
    ```

3. **Update `db.php` with your DB password.**

4. **Copy files to `/var/www/html` on your server.**

5. **Visit `http://your-server-ip/` to register users.**

## Security Notes

- Change DB password before deploying.
- Use HTTPS and secure your server for production.