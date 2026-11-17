# John the Ripper PDF Password Auditing on Kali Linux

## 1. Project Overview

This project demonstrates a practical password-auditing exercise using **John the Ripper** on Kali Linux. The exercise involved extracting a password hash from an authorised, password-protected laboratory PDF, performing a dictionary-based password recovery attempt, and verifying the recovered password by successfully opening the document.

The project demonstrates practical familiarity with password hash extraction, password auditing, Linux command-line operations, and security verification.

## 2. Project Objectives

- Install and verify John the Ripper on Kali Linux.
- Extract a PDF password hash using `pdf2john.pl`.
- Identify the supported PDF hash format.
- Perform a dictionary-based password-auditing exercise.
- Verify the recovery result using John the Ripper.
- Confirm that the recovered password successfully unlocks the PDF.
- Document the methodology and results with screenshots.

## 3. Lab Environment

| Component | Details |
|---|---|
| Host environment | Windows |
| Virtualisation | Oracle VirtualBox |
| Operating system | Kali Linux |
| Password auditing tool | John the Ripper |
| John version | 1.9.0 Jumbo |
| Hash extraction utility | pdf2john.pl |
| Target file | Authorised laboratory PDF |
| Attack method | Dictionary-based password auditing |

## 4. Tools Used

- **Kali Linux:** Linux environment used for the practical exercise.
- **John the Ripper:** Password security auditing tool.
- **pdf2john.pl:** Utility used to extract password hashes from protected PDF documents.
- **Linux Terminal:** Used to execute commands and manage project files.
- **Windows Snipping Tool:** Used to capture project evidence.

## 5. Methodology

### Step 1: Verify John the Ripper Installation

The installation was checked using:

```bash
john
```

John the Ripper launched successfully and displayed its usage information.

### Step 2: Locate the PDF Hash Extraction Utility

The following command was used to locate the PDF extraction utility:

```bash
find /usr/share/john -iname '*pdf*' 2>/dev/null
```

The utility was located at:

```text
/usr/share/john/pdf2john.pl
```

### Step 3: Extract the PDF Password Hash

The authorised laboratory PDF was processed using:

```bash
perl /usr/share/john/pdf2john.pl "$HOME/Desktop/Password-Auditing-Kali-Linux/John-the-Ripper/My Locked PDF1.pdf" > "$HOME/Desktop/Password-Auditing-Kali-Linux/John-the-Ripper/pdf_hash.txt"
```

The extracted hash was saved locally in `pdf_hash.txt`.

### Step 4: Verify PDF Format Support

The available hash formats were checked using:

```bash
john --list=formats | tr ',' '\n' | grep -i pdf
```

The PDF format was successfully identified.

### Step 5: Perform Password Auditing

John the Ripper was executed against the extracted PDF hash:

```bash
john --format=PDF ~/Desktop/Password-Auditing-Kali-Linux/John-the-Ripper/pdf_hash.txt
```

The tool successfully processed the hash using its default password list and recovered the password.

### Step 6: Verify the Recovery Result

The recovery record was checked using:

```bash
john --show --format=PDF ~/Desktop/Password-Auditing-Kali-Linux/John-the-Ripper/pdf_hash.txt | tail -n 1
```

The result confirmed:

```text
1 password hash cracked, 0 left
```

### Step 7: Test the Recovered Password

The recovered password was entered into the protected laboratory PDF. The document opened successfully, confirming that the recovery was valid.

## 6. Results and Findings

The practical exercise was completed successfully.

- John the Ripper recognised the PDF hash format.
- One password hash was successfully recovered.
- The recovery record confirmed one cracked hash and zero remaining.
- The recovered password successfully unlocked the protected PDF.
- The exercise demonstrated how password auditing can identify weak or guessable passwords.

## 7. Screenshots and Evidence

The following screenshots document the practical exercise:

| No. | Evidence |
|---|---|
| 01 | PDF password hash extraction |
| 02 | Successful John the Ripper recovery (redacted) |
| 03 | PDF successfully unlocked |
| 04 | Password recovery verification |

Screenshots are stored in the `Screenshots` directory.

## 8. Key Learning Outcomes

Through this exercise, I gained practical experience in:

- Using John the Ripper in a Kali Linux environment.
- Extracting password hashes from protected PDF files.
- Identifying and working with PDF hash formats.
- Executing dictionary-based password-auditing operations.
- Verifying password recovery results through command-line tools.
- Understanding the importance of strong passwords and secure document protection.
- Maintaining safe handling of recovered credentials and sensitive hash information.

## 9. Security and Ethical Considerations

This exercise was conducted using an authorised laboratory PDF for educational and cybersecurity training purposes.

Password-auditing tools should only be used on files, systems, and accounts for which explicit permission has been granted.

Recovered passwords and sensitive hash values have been excluded from the public project documentation and screenshots.

## 10. Conclusion

This project successfully demonstrated PDF password auditing with John the Ripper on Kali Linux. By extracting the PDF hash, performing a dictionary-based recovery attempt, and verifying the result, I gained practical exposure to Linux-based password auditing and security assessment techniques.

The exercise strengthened my understanding of password security, hash extraction, and the importance of using strong, unique passwords to protect sensitive documents.
