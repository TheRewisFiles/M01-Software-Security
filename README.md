# CS 305 Portfolio Reflection

## Artemis Financial Project Summary

The client for these projects was Artemis Financial, a consulting company that creates individualized financial plans for its customers. These plans include savings, retirement, investments, and insurance. Artemis Financial wanted to modernize its software while improving the security of customer data and financial information. The company specifically wanted stronger protection for its public web application, including secure communications, checksum verification, certificate use, and vulnerability testing.

## What I Did Well

One of the things I did well was carefully reviewing the software for security weaknesses instead of assuming that code was safe because it compiled. In Project One, I reviewed the source code and found issues such as hardcoded database credentials, weak transaction validation, insecure error handling, and outdated third-party dependencies. I also used OWASP Dependency-Check to identify known vulnerabilities in libraries used by the application.

In Project Two, I successfully added security features without breaking the application. I implemented SHA-256 checksum generation, configured HTTPS on port 8443, generated and used a self-signed certificate, and reran dependency testing after the refactoring.

Coding securely is important because software vulnerabilities can expose private information, allow unauthorized access, damage data integrity, or make an application unavailable. Strong software security also helps protect a company’s reputation, reduces the cost of responding to security incidents, and helps maintain customer trust.

## Challenging and Helpful Parts of the Vulnerability Assessment

The most challenging part of the vulnerability assessment was determining the difference between a real security weakness and a potential or conditional vulnerability. Automated tools can report many CVEs, but not every reported vulnerability is necessarily exploitable in a specific application. I had to look at how the code and dependencies were actually being used before deciding how serious a finding was.

The dependency-check process was especially helpful because it showed how much of an application’s security depends on third-party libraries. Even when my own code was small, the application still relied on many external components that could contain known vulnerabilities.

## How I Increased the Layers of Security

I increased the application’s security in several ways. I added SHA-256 checksum verification to help protect data integrity, generated a self-signed RSA certificate, configured the application to use HTTPS, and verified that the secure endpoint worked in a browser. I also used OWASP Dependency-Check to perform static testing after the changes were made.

In the future, I would continue using automated dependency scanners, manual code review, secure coding standards, threat modeling, and vulnerability databases such as the NVD to assess security risks. I would also compare the severity of a vulnerability with how the affected feature is actually used in the application before choosing a mitigation.

## How I Verified the Application Was Functional and Secure

After refactoring the code, I ran the application and confirmed that the `/hash` endpoint worked correctly over HTTPS. The endpoint displayed my unique data string, the SHA-256 algorithm name, and the generated checksum. I also confirmed that the application compiled and ran without syntax or logic errors.

To check whether I introduced new vulnerabilities, I reran OWASP Dependency-Check after the refactoring. The scan still found vulnerabilities in older third-party dependencies that were already part of the supplied project, but the new SHA-256 checksum and HTTPS changes did not introduce additional third-party libraries.

## Resources, Tools, and Coding Practices

The main tools and practices I used included Java, Eclipse, Maven, Java Keytool, SHA-256 with `MessageDigest`, HTTPS configuration in Spring Boot, and OWASP Dependency-Check. I also used secure coding practices such as avoiding obsolete hash algorithms, using standard Java cryptographic APIs instead of creating custom cryptography, manually reviewing code, and testing the application after changes.

These tools and practices will be useful in future projects because they provide a repeatable process for identifying vulnerabilities, applying security improvements, and verifying that those changes work correctly.

## What I Can Show Future Employers

This project demonstrates that I can review an existing Java application, identify software security concerns, refactor code to add security features, configure secure communications, generate certificates, and perform static vulnerability testing. It also shows that I can explain security decisions and document the results of my work.

The completed Artemis Financial Practices for Secure Software Report in this repository provides an example of my ability to apply secure coding practices and evaluate software using both manual and automated security testing techniques.
