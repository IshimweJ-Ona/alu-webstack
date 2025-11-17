## HTTPS & SSL — Project Documentation
This project focuses on DNS configuration, SSL termination with HAProxy, and enforcing HTTPS across a web infrastructure.

# Task 0: World Wide Web
Configure domain DNS records and create a Bash script to audit DNS subdomains.
> DNS Configuration Requirements
- Create the following subdomains:
| Subdomain | Destination    |
| --------- | -------------- |
| `www`     | IP of `lb-01`  |
| `lb-01`   | IP of `lb-01`  |
| `web-01`  | IP of `web-01` |
| `web-02`  | IP of `web-02` |

> Script Requirements
- The script must:
     Accept:
            - domain (required)
            - subdomain (optional)

     Display:
             `The subdomain [SUB_DOMAIN] is a [RECORD_TYPE] record and points to [DESTINATION]`

     When only domain is provided, display the following subdomains in order:
      1. www
      2. lb-01
      3. web-01
      4. web-02
     When domain + subdomain are provided, display only that subdomain.
     Must use:
              - awk
              - at least one Bash function


# Task 1: HAProxy SSL Termination

Enable SSL termination on your load balancer to handle encrypted HTTPS traffic.
> Requirements:
     - Install HAProxy 1.5+
     - HAProxy must:
            - Listen on TCP port 443
            - Accept HTTPS traffic
            - Serve the backend servers via SSL termination
     - The site root (/) must return a page containing: `Holberton School`
     - SSL certificate must be created using certbot

# Task 2: No Loophole in Your Website Traffic
Force all HTTP traffic to automatically redirect to HTTPS
> Requirements:
       - HTTP to HTTPS redirection must be transparent
       - HAProxy must return:
          `HTTP/1.1 301 Moved Permanently`
