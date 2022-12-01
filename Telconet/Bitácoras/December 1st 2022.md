# Telconet Introduction
This sections covers information about the company, like their clients that are part of the company itself, information about the CSOC department, branches of the department, and how Telconet solves client's problems.
# CSOC Department
CSOC (Cyber Security Operation Center) is the department in charge of IR (Incident Response) to their clients, being cataloged by levels:

- Level 1 (High priority)
	- Telconet 
	- Cajamarca
	- Netlife
	- Security Data
	- LinkData
- Level 2 (Medium priority)
	- Bank of Guayaquil
	- Bank of Machala
	- Bank of the coast (Banco del litoral)
	- Medianet
	- Among others...

Being us the MSSP of our clients, we need to prioritize information security of them.

## Verticals
Inside the CSOC department there are sub-departments known as "Vertical" where their duty is to accomplish certain tasks, and these tasks make up the CSOC department, being some of them:
- Infrastructure
- Data Science
- Networking
- CERT (Computer Emergency Response Team)
- Software Development

# Data science vertical 
Data science vertical is based on the idea to use applied statistics oriented to cybersecurity, using these statistics in the denominated "use cases", using tools like:
- Splunk (SIEM)
- Elastic's Kibana (SIEM to implement)
- Elasticsearch (Search & Analytics)
- Logstash

By using these tools we can achieve knowledge of logs to use for example in threat hunting, and by getting these types of data we can achieve a certain "use case".

## Medianet splunk's use cases
- Detection of phishing with NLP without body. (by headers)
- Monitoring of anormal behaviour in the VPN.

### Detection of phishing with NLP without body
This use case is used by an Email Security Gateway (ESG), being in our case FortiMail from Fortinet, and using FortiGuard as the web filter for the URL that is passed on the header of the email, giving the example:
| From               | URL             | Client_Name      |
| ------------------ | --------------- | ---------------- |
| sneder@telconet.ec | www.telconet.ec | mail.telconet.ec |

Thanks to FortiMail, what it does it compares the header's fields to be the same domain, in this case all of them are from the same domain: telconet.ec, meaning that is a secure email to receive and send.

But on the other hand if we have an email with similar fields:
| From               | URL             | Client_Name      |
| ------------------ | --------------- | ---------------- |
| sneder@gmail.com | www.telconet.ec | M24s.google.com |

FortiMail will flag it as a dangerous mail, since all of the headers fields does not come from the same domain, being the URL telconet.ec and the others domains gmail.com, and google.com.

But isn't necessary dangerous, and that is the task to accomplish with NLP, to close the margin of error (errors being like false positives) and create an smart detection of phishing with NLP without the body of the email, only the header.

#### Attachments

![[Phishing-Splunk-Said.pptx]]
