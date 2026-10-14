---
layout: default
title: CV
---

<div style="background: #ffffff; border: 1px solid #e2e8f0; border-top: 4px solid #2563eb; border-radius: 12px; padding: 32px; max-width: 680px; margin: 24px 0; box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05); font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;">

  <div style="margin-bottom: 24px;">
    <h2 style="color: #0f172a; margin: 0 0 8px 0; font-size: 24px; font-weight: 700; tracking: -0.01em;">Request Full Curriculum Vitae</h2>
    <p style="color: #64748b; margin: 0; font-size: 14px; line-height: 1.6;">
      My complete academic CV is available upon request. Please share a few brief details below and I will respond with a PDF copy.
    </p>
  </div>

  <form id="cvForm" onsubmit="sendCVEmail(event)">
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 16px; margin-bottom: 16px;">
      <div>
        <label style="display: block; color: #334155; font-weight: 600; font-size: 13px; text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 6px;">Your Name *</label>
        <input type="text" id="visitorName" required placeholder="Dr. / Mr. / Ms. Full Name" style="width: 100%; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 6px; padding: 10px 14px; color: #0f172a; font-size: 14px; box-sizing: border-box; outline: none; transition: border-color 0.2s;">
      </div>
      <div>
        <label style="display: block; color: #334155; font-weight: 600; font-size: 13px; text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 6px;">Email Address *</label>
        <input type="email" id="visitorEmail" required placeholder="name@institution.edu" style="width: 100%; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 6px; padding: 10px 14px; color: #0f172a; font-size: 14px; box-sizing: border-box; outline: none; transition: border-color 0.2s;">
      </div>
    </div>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 16px; margin-bottom: 16px;">
      <div>
        <label style="display: block; color: #334155; font-weight: 600; font-size: 13px; text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 6px;">Institution / Organization</label>
        <input type="text" id="visitorOrg" placeholder="University or Company name" style="width: 100%; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 6px; padding: 10px 14px; color: #0f172a; font-size: 14px; box-sizing: border-box; outline: none; transition: border-color 0.2s;">
      </div>
      <div>
        <label style="display: block; color: #334155; font-weight: 600; font-size: 13px; text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 6px;">Inquiry Type *</label>
        <select id="visitorPurpose" required style="width: 100%; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 6px; padding: 10px 14px; color: #0f172a; font-size: 14px; box-sizing: border-box; outline: none;">
          <option value="" disabled selected>Select purpose...</option>
          <option value="Research & Academic Collaboration">Research & Academic Collaboration</option>
          <option value="Postdoctoral / Employment Opportunity">Postdoctoral / Employment Opportunity</option>
          <option value="Invited Seminar / Presentation">Invited Seminar / Presentation</option>
          <option value="General Professional Contact">General Professional Contact</option>
        </select>
      </div>
    </div>

    <div style="margin-bottom: 24px;">
      <label style="display: block; color: #334155; font-weight: 600; font-size: 13px; text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 6px;">Additional Notes</label>
      <textarea id="visitorMessage" rows="3" placeholder="Provide any additional context or details..." style="width: 100%; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 6px; padding: 10px 14px; color: #0f172a; font-size: 14px; box-sizing: border-box; resize: vertical; outline: none;"></textarea>
    </div>

    <div style="display: flex; gap: 12px; align-items: center; flex-wrap: wrap; margin-bottom: 16px;">
      <button type="submit" style="background-color: #2563eb; color: #ffffff; border: none; padding: 10px 20px; border-radius: 6px; font-weight: 600; font-size: 14px; cursor: pointer; box-shadow: 0 1px 2px rgba(0,0,0,0.05);">Submit Request</button>
      <button type="button" onclick="copyEmailAddress()" style="background-color: #f1f5f9; color: #334155; border: 1px solid #cbd5e1; padding: 10px 20px; border-radius: 6px; font-weight: 600; font-size: 14px; cursor: pointer;">Copy Direct Email</button>
      <span id="copyNotice" style="color: #16a34a; font-size: 13px; font-weight: 600; display: none;">✓ Email copied to clipboard</span>
    </div>

    <p style="color: #94a3b8; font-size: 12px; margin: 0; line-height: 1.4;">
      <em>Note: Clicking "Submit Request" opens your primary email client with a formatted message addressed to Dr. Tipu.</em>
    </p>
  </form>
</div>

<script>
function sendCVEmail(event) {
  event.preventDefault();
  
  const name = document.getElementById('visitorName').value;
  const email = document.getElementById('visitorEmail').value;
  const org = document.getElementById('visitorOrg').value || 'Not specified';
  const purpose = document.getElementById('visitorPurpose').value;
  const message = document.getElementById('visitorMessage').value || 'None';
  
  const myEmail = "mtipu@umd.edu";
  const subject = encodeURIComponent(`CV Request from ${name} [${org}]`);
  const body = encodeURIComponent(
    `Dear Dr. Tipu,\n\nI am writing to request a copy of your full Curriculum Vitae.\n\n` +
    `--- Contact Information ---\n` +
    `Name: ${name}\n` +
    `Email: ${email}\n` +
    `Organization / Institution: ${org}\n` +
    `Inquiry Type: ${purpose}\n\n` +
    `--- Additional Details ---\n${message}\n\n` +
    `Sincerely,\n${name}`
  );

  window.location.href = `mailto:${myEmail}?subject=${subject}&body=${body}`;
}

function copyEmailAddress() {
  const email = "mtipu@umd.edu";
  navigator.clipboard.writeText(email).then(() => {
    const notice = document.getElementById('copyNotice');
    notice.style.display = 'inline';
    setTimeout(() => { notice.style.display = 'none'; }, 3000);
  });
}
</script>

---

## Brief Academic Overview

### Current Position
* **Postdoctoral Associate** — Department of Plant Science and Landscape Architecture, University of Maryland, College Park

### Education
* **Ph.D. in Horticulture** — Virginia Tech, Blacksburg, VA
* **M.S. in Plant Pathology** — Bangladesh Agricultural University, Mymensingh
* **B.S. in Agriculture (Honours)** — Bangladesh Agricultural University, Mymensingh

### Professional Experience
* **Scientific Officer / Research Assistant** (2013 – 2022)  
  Bangladesh Agricultural Research Institute (BARI), Gazipur, Bangladesh

### Awards & Honors
* **P. Howard & Betsy Massey Horticulture Scholarship** — Virginia Tech, USA
* **Student Travel Award** — 10th Annual UF Plant Science Symposium, University of Florida, USA
* **Symposium Travel Grant** — 2026 Cornell Corteva Plant Breeding Symposium, Cornell University, USA
* **OKP Scholarship** — Wageningen Centre for Development Innovation, Netherlands
* **NEB Molecular Biology Summer Scholarship** — New England Biolabs, USA
