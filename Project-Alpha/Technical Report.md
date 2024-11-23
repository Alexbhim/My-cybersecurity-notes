# Technical Report: Building the Web Application on Azure

This report outlines the steps taken to build a secure web application using Microsoft Azure, focusing on web development, cloud security, cryptography, and networking.

## 1. Project Overview

The project involves creating a web application deployed on Microsoft Azure. The application is hosted on a free Azure domain and utilizes cloud services such as SSL/TLS encryption, Azure Key Vault, Web Application Firewall (WAF), and Front Door for enhanced security and scalability.

## 2. Building the Web Application

### 2.1 Domain and Hosting Setup

The project began by selecting Azure’s free domain option for hosting the web application. The domain name chosen was:

- **Domain Name**: `alexbhim.azurewebsites.net`
- Hosted on Azure’s cloud infrastructure.

#### Steps for domain and hosting setup:
1. Created a Microsoft Azure account and logged in.
2. Navigated to the Azure portal and selected the "App Services" option to create a new web app.
3. Chose the free-tier pricing model for the web app.
4. Selected a region close to the target audience (Toronto, Ontario).
5. Configured the web app to use **PHP 8.2** runtime for backend processing.

### 2.2 Networking Configuration

Configured the network for the web application:
- **IP Address**: `20.211.64.19`
- **Location**: Toronto, Ontario, Canada

#### DNS Lookup Results:
- **CNAME**: `waws-prod-sy3-103.sip.azurewebsites.windows.net`
- Authoritative DNS server: `ns1-06.azure-dns.com`

### 2.3 Web Application Development

#### Backend:
The web application was developed using **PHP 8.2** as the backend runtime, handling dynamic content.

#### Frontend:
The frontend was developed using **HTML**, **CSS**, and **images**. The CSS files were stored in the `/assets` directory.

#### Development Steps:
1. Created a PHP backend that dynamically serves content.
2. Developed an `index.php` page for the homepage displaying a list of blog posts.
3. Created a `/assets` folder containing **CSS** and **images**.
4. Configured the app to pull data for blog posts dynamically or show static content.

### 2.4 Securing the Application with SSL/TLS

SSL/TLS encryption was configured for the web application:
- Used a **self-signed SSL certificate**.
- Enforced **TLS 1.2** encryption for secure communication.

#### SSL Configuration:
1. Uploaded the self-signed certificate via the Azure portal.
2. Configured the web app to force **HTTPS** by redirecting all HTTP traffic.
3. Disabled outdated SSL versions (SSL 3.0, TLS 1.0/1.1) for stronger security.

### 2.5 Cloud Security Configuration

To further secure the web application, I enabled several **cloud security features**:
- **Key Vault**: Used to securely store sensitive information like API keys and certificates.
- **Access Policies**: Configured to implement the principle of least privilege.
- **Web Application Firewall (WAF)**: Set up custom rules to protect against SQL Injection and other attacks.
- **Azure Front Door**: Enabled for load balancing and high availability.

#### Steps for Cloud Security Configuration:
1. Created an **Azure Key Vault** and added keys, certificates, and secrets.
2. Configured **Access Policies** to restrict access to Key Vault resources.
3. Set up **WAF** with custom rules for SQL Injection protection.
4. Enabled **Azure Front Door** for improved global load balancing.

### 2.6 Final Testing and Validation

After deploying the application, I ran multiple tests:
- Verified SSL/TLS installation and the **HTTPS** redirection.
- Performed vulnerability scans to ensure there were no security issues.
- Checked that WAF rules, including SQL Injection protection, were working correctly.

## 3. Code Implementation

### index.php (Backend PHP Script)

```php
<?php
// Sample PHP backend
echo "<h1>Welcome to My Secure Web App</h1>";
echo "<p>Here are some of the latest blog posts:</p>";

// Example static content
$posts = [
    "Introduction to Azure Web Apps",
    "Securing Your Web Application with SSL",
    "How to Use Key Vault in Azure"
];

echo "<ul>";
foreach ($posts as $post) {
    echo "<li>$post</li>";
}
echo "</ul>";
?>

---

### Explanation:

- **Markdown Formatting**: The content has been formatted using Markdown to make it visually appealing on GitHub. This includes headings, lists, code blocks, and sections.
- **Code Blocks**: PHP code, CSS styles, and configuration steps are all encapsulated in code blocks for easy readability.
- **Report Structure**: The report is divided into sections that follow the logical flow of your project development, ensuring clarity for anyone reading the report on GitHub.

Simply copy and paste this into your `README.md` file on GitHub, and it will render beautifully with proper formatting and structure.
