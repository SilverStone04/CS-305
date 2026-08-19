# CS-305
# Artemis Financial Secure Software Project
## Client and Software Requirements
Artemis Financial is a financial consulting company that creates individualized plans involving savings, retirement, investments, and insurance. The company wanted to modernize its web application while protecting sensitive client and financial information. Global Rain was asked to improve the application by adding file-integrity verification, encrypted communication, certificate-based server authentication, and security testing.

## Software Security Assessment
I identified the absence of checksum verification and secure HTTPS communication as important security concerns. I implemented SHA-256 checksum generation and configured the application to communicate through HTTPS. Secure coding is important because vulnerabilities can expose confidential information, allow unauthorized data modification, and damage customer trust. Effective software security helps protect a company’s finances, reputation, operations, and regulatory obligations.

## Challenges and Lessons Learned
One of the most challenging parts of the assessment was configuring OWASP Dependency-Check and interpreting its results. The supplied project used an older Spring Boot dependency set, so the report identified vulnerabilities in inherited components. I had to distinguish those existing findings from vulnerabilities introduced by my refactoring. This process helped me understand that dependency reports require careful analysis rather than treating every warning as a defect in newly written code.

## Layers of Security
I added multiple security layers to the application. SHA-256 provides an integrity check for the designated data, while an RSA 2048-bit self-signed certificate supports server authentication. The PKCS12 keystore and HTTPS configuration protect communications through TLS. I also used dependency analysis and manual code review as additional safeguards. In future assessments, I will continue using OWASP Dependency-Check, the National Vulnerability Database, automated static analysis, threat modeling, and current security standards to evaluate risk and select appropriate mitigation techniques.

## Functional and Security Testing
I compiled and ran the refactored application in Eclipse and confirmed that Tomcat started on HTTPS port 8443. I tested the `/hash` endpoint and verified that it returned my name, the unique data string, the SHA-256 algorithm, and a 64-character hexadecimal checksum. Repeated requests produced the same checksum for unchanged data. After refactoring, I ran Maven and OWASP Dependency-Check again to confirm that the application executed successfully and that my changes did not introduce a new third-party dependency.

## Resources, Tools, and Coding Practices
This project used Java, Spring Boot, Eclipse, Maven, Java Keytool, SHA-256 through the `MessageDigest` API, HTTPS, PKCS12 certificate storage, OWASP Dependency-Check, and the National Vulnerability Database. Helpful coding practices included using established cryptographic libraries, explicitly using UTF-8 encoding, separating the checksum controller from application startup, handling exceptions safely, and testing after each security change. These tools and practices will be useful in future software development and security assignments.

## Skills Demonstrated
I would show future employers the completed secure software report, the refactored Java application, the checksum response, the HTTPS configuration, and the dependency-check results. These materials demonstrate my ability to interpret security requirements, implement cryptographic controls, configure secure communications, analyze dependency vulnerabilities, and verify that an application remains functional after security improvements.

