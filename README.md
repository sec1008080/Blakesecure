# Blakesecure
Website for Blake=Secure that is local and  provides inperson system recovery for compromised devices &amp; investigation of malicious activity.



from fpdf import FPDF

pdf = FPDF()
pdf.add_page()
pdf.set_auto_page_break(auto=True, margin=15)

pdf.set_font("Helvetica", "B", 16)
pdf.cell(0, 10, "Authorization for Mobile Device Investigation and Network Analysis", new_x="LMARGIN", new_y="NEXT", align="C")
pdf.ln(10)
pdf.set_font("Helvetica", "", 12)

sections = [
    ("Date:", ""),
    ("Case/Reference Number:", ""),
    ("\n1. Subject Information", ""),
    ("Name:", ""), ("Phone Number(s):", ""), ("Device Make/Model:", ""), ("IMEI / Serial Number:", ""),
    ("\n2. Purpose of Authorization",
     "This authorization grants permission to perform a forensic and network analysis of the above-listed "
     "mobile device(s) and related data. The investigation is being initiated due to a suspected security "
     "compromise potentially involving unauthorized access, interception, or manipulation of communications, "
     "possibly through SS7 or other signaling vulnerabilities."),
    ("\n3. Scope of Investigation",
     "Authorized investigators are permitted to:\n"
     "1. Access and analyze device storage, applications, logs, and configurations.\n"
     "2. Capture and inspect network traffic associated with the device, including IP and SS7-related signaling data.\n"
     "3. Collect and preserve evidence in a forensically sound manner.\n"
     "4. Document findings and prepare a report outlining any evidence of compromise."),
    ("\n4. Consent and Authorization",
     "I, the undersigned, am the lawful owner or authorized custodian of the device(s) listed above and hereby grant "
     "permission for the investigation and data analysis as outlined in this document.\n\n"
     "I understand that:\n"
     "- The analysis may involve accessing sensitive personal and communication data.\n"
     "- All findings will be handled confidentially and used solely for investigative and security purposes.\n"
     "- This authorization remains valid until the investigation is concluded or revoked in writing."),
    ("\n5. Investigator / Organization Information", ""),
    ("Investigator / Analyst Name:", ""), ("Organization / Agency:", ""), ("Contact Information:", ""),
    ("\n6. Signatures",
     "Device Owner / Authorized Party:\nSignature: _______________________________\n"
     "Printed Name: ____________________________   Date: ____________________________\n\n"
     "Investigator / Analyst:\nSignature: _______________________________\n"
     "Printed Name: ____________________________   Date: ____________________________"),
    ("\n7. Optional – Legal Acknowledgment",
     "This investigation is authorized under applicable laws governing digital forensics and network security "
     "assessments. Unauthorized interception or analysis of communications beyond the scope of this consent is prohibited.")
]

for title, text in sections:
    pdf.set_font("Helvetica", "B", 12)
    pdf.multi_cell(0, 8, title)
    pdf.set_font("Helvetica", "", 12)
    if text:
        pdf.multi_cell(0, 8, text)

pdf.output("Authorization_Form_Mobile_Investigation.pdf")
print("✅ PDF created: Authorization_Form_Mobile_Investigation.pdf")
