---
layout: default
title: CV
---

<div style="background-color: #121814; color: #e2e8f0; padding: 28px; border-radius: 16px; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; max-width: 680px; margin: 20px 0; box-shadow: 0 10px 25px rgba(0,0,0,0.3);">

  <h2 style="color: #ffffff; margin-top: 0; margin-bottom: 8px; font-size: 26px; font-weight: 700;">Request the full CV</h2>
  <p style="color: #94a3b8; margin-bottom: 24px; font-size: 15px; line-height: 1.5;">
    My full CV is not posted publicly. Tell me a little about yourself and I will reply with a copy, usually within a few days.
  </p>

  <form id="cvForm" onsubmit="sendCVEmail(event)">
    <div style="display: flex; gap: 16px; margin-bottom: 16px; flex-wrap: wrap;">
      <div style="flex: 1; min-width: 240px;">
        <label style="display: block; color: #f1f5f9; font-weight: 600; font-size: 14px; margin-bottom: 6px;">Your name *</label>
        <input type="text" id="visitorName" required style="width: 100%; background: #1a221d; border: 1px solid #334155; border-radius: 8px; padding: 10px 12px; color: #ffffff; font-size: 14px; box-sizing: border-box; outline: none;">
      </div>
      <div style="flex: 1; min-width: 240px;">
        <label style="display: block; color: #f1f5f9; font-weight: 600; font-size: 14px; margin-bottom: 6px;">Your email *</label>
        <input type="email" id="visitorEmail" required style="width: 100%; background: #1a221d; border: 1px solid #334155; border-radius: 8px; padding: 10px 12px; color: #ffffff; font-size: 14px; box-sizing: border-box; outline: none;">
      </div>
    </div>

    <div style="display: flex; gap: 16px; margin-bottom: 16px; flex-wrap: wrap;">
      <div style="flex: 1; min-width: 240px;">
        <label style="display: block; color: #f1f5f9; font-weight: 600; font-size: 14px; margin-bottom: 6px;">Organization</label>
        <input type="text" id="visitorOrg" style="width: 100%; background: #1a221d; border: 1px solid #334155; border-radius: 8px; padding: 10px 12px; color: #ffffff; font-size: 14px; box-sizing: border-box; outline: none;">
      </div>
      <div style="flex: 1; min-width: 240px;">
        <label style="display: block; color: #f1f5f9; font-weight: 600; font-size: 14px; margin-bottom: 6px;">Purpose *</label>
        <select id="visitorPurpose" required style="width: 100%; background: #1a221d; border: 1px solid #334155; border-radius: 8px; padding: 10px 12px; color: #ffffff; font-size: 14px; box-sizing: border-box; outline: none;">
          <option value="" disabled selected>Select one</option>
          <option value="Academic Collaboration">Academic Collaboration</option>
          <option value="Job / Recruitment Opportunity">Job / Recruitment Opportunity</option>
          <option value="Speaking / Invited Talk">Speaking / Invited Talk</option>
          <option value="General Inquiry">General Inquiry</option>
        </select>
      </div>
    </div>

    <div style="margin-bottom: 24px;">
      <label style="display: block; color: #f1f5f9; font-weight: 600; font-size: 14px; margin-bottom: 6px;">Message</label>
      <textarea id="visitorMessage" rows="4" placeholder="Anything that helps me respond (optional)" style="width: 100%; background: #1a221d; border: 1px solid #334155; border-radius: 8px; padding: 10px 12px; color: #ffffff; font-size: 14px; box-sizing: border-box; resize: vertical; outline: none;"></textarea>
    </div>

    <div style="display: flex; gap: 12px; align-items: center; flex-wrap: wrap; margin-bottom: 20px;">
      <button type="submit" style="background-color: #22c55e; color: #052e16; border: none; padding: 12px 24px; border-radius: 24px; font-weight: 700; font-size: 15px; cursor: pointer; transition: background-color 0.2s;">Send request</button>
      <button type="button" onclick="copyEmailAddress()" style="background-color: transparent; color: #ffffff; border: 1px solid #475569; padding: 12px 24px; border-radius: 24px; font-weight: 600; font-size: 15px; cursor: pointer;">Copy my email address</button>
      <span id="copyNotice" style="color: #4ade80; font-size: 13px; display: none;">Copied to clipboard!</span>
    </div>

    <p style="color: #64748b; font-size: 13px; margin: 0;">
      Sending opens your email app with the request already written. Nothing is stored on this website.
    </p>
  </form>
</div>

<script>
function sendCVEmail(event) {
  event.preventDefault();
  
  const name = document.getElementById('visitorName').value;
  const email = document.getElementById('visitorEmail').value;
  const org = document.getElementById('visitorOrg').value || 'N/A';
  const purpose = document.getElementById('visitorPurpose').value;
  const message = document.getElementById('visitorMessage').value || 'N/A';
  
  const myEmail = "mtipu@umd.edu";
  const subject = encodeURIComponent(`CV Request: ${name} (${org})`);
  const body = encodeURIComponent(
    `Hello Dr. Tipu,\n\nI would like to request a copy of your full CV.\n\n` +
    `-- Request Details --\n` +
    `Name: ${name}\n` +
    `Email: ${email}\n` +
    `Organization: ${org}\n` +
    `Purpose: ${purpose}\n\n` +
    `Message / Context:\n${message}\n\n` +
    `Best regards,\n${name}`
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
