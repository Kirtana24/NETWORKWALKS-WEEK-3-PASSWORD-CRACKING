# PDF Password Security: Hash Extraction, Analysis & Dictionary Attacks

**Cybersecurity Internship | Networkwalks | Week 03**

## 1. Project Overview

This repository contains the documentation of my Week 03 practical activities completed as part of the Networkwalks Cybersecurity Internship, focusing on PDF password cracking, hash extraction, and dictionary-based password attacks.

The main aim of this exercise was to gain practical knowledge of how password-protected PDF files are secured, how their password hashes can be extracted, and how password auditing tools are used to identify matching passwords through dictionary-based techniques.

The practical work was divided into two modules:

**Module 1: John the Ripper and Johnny GUI**

Exploring John the Ripper and its graphical interface, Johnny, for password auditing. This involved configuring the tool, importing an extracted PDF hash, performing a dictionary attack, and attempting to recover the document password.

**Module 2: Networkwalks Hash Analysis Tools**

Working with the Networkwalks Hash Calculator to extract password hashes from encrypted PDF files and using the Networkwalks Comparison Tool to test password candidates through dictionary-based comparison. Additionally, Online Hash Crack was explored as another utility for PDF hash extraction.

### Objectives

- Understand PDF password protection.
- Learn the process of PDF hash extraction.
- Perform dictionary-based password attacks.
- Use John the Ripper for password auditing.
- Understand how password hashes are analyzed.
- Identify weak and predictable passwords.
- Verify recovered passwords against protected PDF documents.

---

## 2. Lab Environment

| Parameter | Details |
|---|---|
| Trainee | Kirtana Minoy |
| Organization | Networkwalks |
| Program/Batch | B084D |
| Week | Week 03 |
| Operating System | Kali Linux |
| Virtualization | Oracle VirtualBox |
| Primary Tool | John the Ripper |
| Hash Extraction Tool | Networkwalks Hash Calculator |
| Comparison Tool | Networkwalks Comparison Tool |
| Target File | Password-protected PDF |
| Domain | Cybersecurity & Ethical Hacking |

---
### Test Documents Used

The practical exercises involved two password-protected PDF files, with each document assigned to a separate module:

- **Module 1:** `My Locked PDF1.pdf` – Used to extract the PDF hash and perform password auditing using John the Ripper through the Johnny GUI.
- **Module 2:** `My Locked PDF2.pdf` – Used to generate the PDF hash with the Networkwalks Hash Calculator and perform dictionary-based password comparison using the Networkwalks Comparison Tool.

---

## 3. Module 1: John the Ripper with Johnny GUI

### 3.1 Tools and Technologies

**John the Ripper (Jumbo Edition)**

John the Ripper is an open-source password auditing utility designed to identify weak passwords by testing different password candidates against stored hashes. It supports a wide range of hash formats and password-testing methods, including dictionary attacks.

The Jumbo edition offers extended functionality and support for additional hash formats compared to the core version.

**Johnny GUI**

Johnny is a graphical interface developed for John the Ripper. It provides a visual way to manage password auditing activities, allowing users to configure settings, load hash files, and monitor cracking progress without depending entirely on terminal commands.

**PDF Hash Extraction Utility**

A PDF hash extraction utility is used to retrieve password-related hash information from an encrypted PDF document. The extracted hash is then provided to John the Ripper for password auditing.

### 3.2 Practical Implementation

**Step 1: Downloading and Extracting John the Ripper**

Downloaded the Windows 64-bit Jumbo version of John the Ripper and extracted the downloaded archive to access its required files.

The main executable needed to connect Johnny with the John the Ripper engine is:

`john.exe`

It was available inside the extracted `run` directory at the following location:

`C:\Users\DELL\Downloads\john-1.9.0-jumbo-1-win64\john-1.9.0-jumbo-1-win64\run\john.exe`

**Step 2: Configuring John the Ripper in Johnny GUI**

Opened the Settings section in Johnny and selected the Browse option to specify the location of the `john.exe` executable.

Navigated to the extracted `run` folder and selected the executable file.

After configuration, Johnny identified the installed John the Ripper version:

`John the Ripper 1.9.0-jumbo-1 OMP [cygwin 64-bit x86_64 AVX2 AC]`

This verified that Johnny was correctly connected to the John the Ripper password auditing engine and was ready for further configuration.

<img width="870" height="687" alt="AdobeExpressPhotos_50b062f35198482c898f8f25f559d8ee_CopyEdited" src="https://github.com/user-attachments/assets/b84b8d5d-b665-4844-8e4b-250dd9bd7d13" />

**Observation:** Johnny provides the graphical interface for managing the process, whereas John the Ripper handles the actual password auditing. Therefore, selecting the correct executable is necessary for both tools to work together properly.

**Step 3: Extracting the PDF Hash**

Selected the authorized password-protected PDF document and processed it using a PDF hash extraction utility.

The utility generated a hash in the specialized PDF format:

`$pdf$4*4*128*-102...`

This extracted representation contains the password-verification information required by compatible auditing tools to test possible password combinations.

**Step 4: Importing the Extracted Hash into Johnny**

Launched Johnny and selected the **Open password file** option to import the text file containing the extracted PDF hash.

Selected the appropriate hash format and loaded the file into the application.

The extracted entry appeared in the Passwords section, with the hash successfully populated and its format identified as **PDF**.

At this point, no password had been recovered. The status bar displayed:

`0% (0/1: 0 cracked, 1 left) [format=PDF]`

This indicated that one password hash had been loaded successfully and was awaiting the password auditing process.

<img width="1600" height="730" alt="WhatsApp Image 2026-11-19 at 11 13 24 AM" src="https://github.com/user-attachments/assets/e2f30503-7956-4c81-b842-cbe41a178ba4" />

**Step 5: Initiating the Dictionary Attack**

After loading the extracted PDF hash, selected the **Start new attack** option in Johnny to launch the dictionary-based password auditing process.

John the Ripper's underlying engine began testing password candidates against the loaded `$pdf$` hash to identify a matching password.

**Step 6: Recovering the PDF Password**

The dictionary attack successfully identified the password corresponding to the loaded hash.

Johnny displayed the recovered password in the Password column:

`good-luck`

The status bar showed the following result:

`100% (1/1: 1 cracked, 0 left) [format=PDF]`

This confirmed that the password auditing process was completed successfully and the single loaded PDF hash had been cracked.

<img width="867" height="686" alt="WhatsApp Image 2026-11-19 at 11 18 59 AM" src="https://github.com/user-attachments/assets/04ec5d9f-626a-48ea-8aee-93b930e0f07b" />

**Step 7: Capturing the Module 1 Flag**

After successfully recovering the PDF password and completing the practical exercise, the Networkwalks training platform displayed the following flag as confirmation of successful completion:

`nw{cybersecurity_flag_captured_2608}`

<img width="1600" height="721" alt="WhatsApp Image 2026-11-19 at 11 20 17 AM" src="https://github.com/user-attachments/assets/9f269796-323e-4950-b584-175ae614f8d7" />

<img width="640" height="897" alt="image" src="https://github.com/user-attachments/assets/d485f11b-33d2-454e-820f-7a2fa5d4e60c" />

Through this module, I gained practical experience in using Johnny as a graphical interface for John the Ripper, from configuring the executable and importing the extracted PDF hash to initiating the dictionary attack and recovering the password successfully. The exercise also highlighted the importance of selecting the correct hash format and ensuring proper tool configuration before performing a password security assessment.

## 4. Module 2: PDF Hash Extraction Using Networkwalks Tools

### 4.1 Tools Used

**Networkwalks Hash Calculator**

A web-based utility designed to generate cryptographic hashes from text and files, along with extracting password-related hashes from encrypted PDF documents.

The interface also indicates that PDF processing takes place locally within the browser.

**Networkwalks Comparison Tool**

A password auditing utility that takes an extracted PDF hash as input and compares it against possible password candidates using a predefined dictionary.

**Online Hash Crack**

An additional online utility used to extract password hash representations from encrypted PDF files. The generated hashes are compatible with PDF password auditing tools such as `pdf2john` and Hashcat.

### 4.2 Practical Implementation

**Step 1: Opening the Networkwalks Hash Calculator**

Accessed the Networkwalks Hash Calculator through the provided internship resource.

The interface offers three input options for different hashing operations:

- **Text:** Generates supported cryptographic hashes from entered text.
- **File:** Performs hash-related operations on uploaded files.
- **PDF:** Extracts password-related hash information from encrypted PDF documents.

Selected the **PDF** option to proceed with the extraction exercise.

**Step 2: Uploading the Encrypted PDF**

Uploaded the assigned password-protected document, `My Locked PDF2.pdf` (204.7 KB), from the local system.

After processing the file, the calculator identified it as an encrypted PDF and displayed the following notification:

> "This PDF is encrypted. A crackable hash has been extracted below (pdf2john / hashcat compatible format)."

The tool then generated a PDF hash representation that could be used with compatible password auditing utilities.

The extracted document information included the following parameters:

| **Parameter** | **Observed Value** |
|---|---|
| Document Type | Encrypted PDF |
| Hash Format | PDF / pdf2john-compatible |
| Revision | R4 |
| PDF Version | V4 |
| Encryption Key Length | 128 bit |

These values provide information about the document's encryption settings and help determine the appropriate format for subsequent password auditing.

<img width="1600" height="723" alt="WhatsApp Image 2026-11-19 at 11 24 09 AM" src="https://github.com/user-attachments/assets/0db7fc16-def1-4592-b3dd-144967d40951" />



**Step 3: Understanding the Extracted PDF Hash**

The extracted `$pdf$...` string contains the information required by compatible password-auditing tools to verify password candidates.

This extracted value is not the actual PDF password. Instead, it serves as the input for the password-testing process.

Therefore, PDF hash extraction and password comparison are two separate stages of the auditing process.

**Step 4: Exploring Online Hash Crack**

To explore an alternative method of PDF hash extraction, I also used the **PDF Hash Extractor** available on Online Hash Crack, described as "Extract a PDF hash for a controlled test".

I selected the encrypted document (`My Locked PDF2.pdf`) using the **Choose file** option.

After uploading the file, the utility processed it and displayed the following confirmation message:

> "Extraction complete. Review the output before using it in an authorized test."

The extracted output was designed for use with compatible PDF password-auditing tools such as `pdf2john` and Hashcat.

The website also mentioned that uploaded files are processed for extraction and subsequently deleted. It specified a maximum upload size of 100 MB.

<img width="1280" height="578" alt="WhatsApp Image 2026-11-19 at 12 16 44 PM" src="https://github.com/user-attachments/assets/e55d4d0a-c3ca-4a93-b809-aee96ea1824c" />



**Step 5: Accessing the Networkwalks Comparison Tool**

After extracting the PDF hash using the Networkwalks Hash Calculator, I accessed the **Comparison Tool**, available under the "Password Cracker through Dictionary Attacks" lab.

The tool takes the extracted PDF hash as input and compares it against a predefined list of possible passwords. It follows the same basic dictionary-attack concept used by tools such as John the Ripper.

**Step 6: Submitting the Hash for Comparison**

I pasted the extracted PDF hash into the designated input field and started the comparison process using the tool's built-in dictionary containing 100 candidate passwords.

During the process, the interface provided real-time information, including:

- Number of password candidates attempted through a progress bar.
- Total number of candidates in the dictionary.
- Processing speed in password attempts per second.
- Overall progress percentage.
- Individual password candidates being tested, such as `secret`, `pepper`, `ginger`, `maggie`, `access`, `flower`, `cookie`, `banana`, `orange`, and `purple`.

During the observed execution, the tool had tested 91 out of 100 candidates, showing 91% progress at approximately 9 password attempts per second.

**Step 7: Observing the Successful Password Match**

The Comparison Tool subsequently displayed a **"Password Cracked Successfully"** notification, indicating that a matching password had been identified.

The interface also instructed me to open the PDF and enter the recovered password to unlock the document. For security and documentation purposes, the actual matched password was redacted in the repository screenshot.

<img width="1280" height="582" alt="WhatsApp Image 2026-11-19 at 12 18 49 PM" src="https://github.com/user-attachments/assets/7ff68d38-5a58-493e-acbb-1e0c0cbdb6d8" />

**Step 8: Capturing the Module 2 Flag**

After completing the assigned password security exercise successfully, the Networkwalks training platform displayed the following completion confirmation:

`nw{networkwalks_persistence_jtr_270521}`

**Step 9: Verifying the Recovered Password**

I used the recovered password to open the corresponding password-protected training document in a PDF viewer.

The viewer displayed an **"Enter a password"** prompt. After entering the recovered password, the document was successfully unlocked, confirming that the password was correct.

<img width="1600" height="721" alt="WhatsApp Image 2026-11-19 at 11 31 01 AM" src="https://github.com/user-attachments/assets/ee8bf095-a78a-4ffe-8c14-0ac88c6d1aeb" />

<img width="647" height="782" alt="WhatsApp Image 2026-11-19 at 11 32 47 AM" src="https://github.com/user-attachments/assets/04992e9f-c6c8-4878-87bb-372290c273cb" />

The password was cracked and the pdf opened successfully.

## 5. Flag Capture and Completion

| Module | Tool Used | Completion |
|---|---|---|
| Module 1 | John the Ripper | To be updated |
| Module 2 | Networkwalks Hash Calculator and Comparison Tool | To be updated |

---

## 6. Comparative Analysis of the Tools

The practical exercise involved several tools and utilities, each contributing to a specific stage of the PDF password-auditing process.

| **Tool** | **Primary Function** | **Practical Application** |
|---|---|---|
| John the Ripper | Password auditing engine | Processes extracted hashes and tests possible password candidates. |
| Johnny | Graphical interface | Provides a GUI to configure and manage John the Ripper. It also displayed the recovered password (`good-luck`). |
| Networkwalks Hash Calculator | Hash extraction and generation | Extracts password-related hash information from encrypted PDF files (`My Locked PDF2.pdf`). |
| Networkwalks Comparison Tool | Dictionary-based comparison | Compares extracted hashes against candidate passwords and displays live progress and processing-speed details. |
| Online Hash Crack | PDF hash extraction | Generates PDF hash representations compatible with password-auditing tools (`My Locked PDF1.pdf`). |
| Adobe Acrobat / Edge PDF Viewer | Password verification | Verifies the recovered password by confirming that it successfully unlocks the original protected document. |


---

## 7. Key Observations and Results

1. Password-protected PDF documents require appropriate hash extraction before password auditing.
2. Extracted hashes are different from plaintext passwords.
3. John the Ripper supports multiple hash formats.
4. Dictionary attacks test predefined password candidates.
5. The correct hash format is important for successful password auditing.
6. The Networkwalks Hash Calculator simplifies the PDF hash extraction process.
7. The Comparison Tool demonstrates dictionary-based password testing.
8. Successful password recovery should be verified against the original PDF document.
9. Weak and predictable passwords can make encrypted documents vulnerable to dictionary attacks.

---

## 8. Key Learnings

**1. PDF Password Security**

Understood how passwords protect PDF documents and how password verification works.

**2. Hash Extraction**

Learned how password-related hash information can be extracted from encrypted PDF files.

**3. John the Ripper**

Gained practical experience in using John the Ripper for password auditing.

**4. Dictionary Attacks**

Understood how predefined password lists are used to test possible passwords.

**5. Hash Formats**

Learned the importance of selecting compatible hash formats for password auditing tools.

**6. Tool Integration**

Explored how hash extraction and password comparison tools work together.

**7. Password Strength**

Understood why long, unique, and unpredictable passwords are important for document security.

---

## 9. Security Recommendations

- Use strong and unique passwords.
- Avoid commonly used passwords and predictable patterns.
- Use appropriate PDF encryption settings.
- Avoid reusing passwords across documents.
- Store passwords securely.
- Conduct password auditing only with proper authorization.

---

## 10. Conclusion

During Week 03 of my Cybersecurity and Ethical Hacking internship, I explored PDF password security, hash extraction, and dictionary-based password auditing.

In the first module, I worked with John the Ripper to understand how extracted PDF hashes can be processed and tested using dictionary-based attacks.

In the second module, I explored the Networkwalks Hash Calculator and Comparison Tool to understand PDF hash extraction and password comparison.

Overall, this practical helped me understand the relationship between password protection, hash extraction, password auditing, and document verification. It also highlighted the importance of using strong and unpredictable passwords to protect sensitive documents.

---

## 11. Disclaimer

This repository is maintained for educational purposes as part of the Networkwalks Cybersecurity Internship.

All activities are intended for authorized training documents and controlled learning environments.

The techniques demonstrated must only be used for legitimate security testing with appropriate permission.

---

## 12. Author Information

**Kirtana Minoy**

Cybersecurity & Ethical Hacking Intern | Networkwalks

| Detail | Information |
|---|---|
| Internship | Networkwalks |
| Week | 03 |
| Domain | Cybersecurity & Ethical Hacking |
| Topic | PDF Password Cracking and Hash Extraction |

**Repository Purpose:** Documentation of Week 03 practical exercises, implementation steps, screenshots, and cybersecurity learnings.
