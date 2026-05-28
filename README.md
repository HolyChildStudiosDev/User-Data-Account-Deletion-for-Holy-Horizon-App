<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Delete Account – Holy Horizon</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #e0f2fe 0%, #bae6fd 100%);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
    }
    .card {
      background: white;
      border-radius: 16px;
      padding: 40px;
      max-width: 480px;
      width: 100%;
      box-shadow: 0 4px 24px rgba(0,0,0,0.10);
    }
    .logo {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 24px;
    }
    .logo-icon {
      width: 40px;
      height: 40px;
      background: linear-gradient(135deg, #0ea5e9, #3b82f6);
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 22px;
    }
    .logo-text {
      font-size: 20px;
      font-weight: 700;
      color: #0c4a6e;
    }
    h1 {
      font-size: 22px;
      font-weight: 700;
      color: #0c4a6e;
      margin-bottom: 8px;
    }
    p.subtitle {
      color: #64748b;
      font-size: 14px;
      margin-bottom: 28px;
      line-height: 1.6;
    }
    label {
      display: block;
      font-size: 13px;
      font-weight: 600;
      color: #374151;
      margin-bottom: 6px;
    }
    input, textarea, select {
      width: 100%;
      padding: 10px 14px;
      border: 1.5px solid #e2e8f0;
      border-radius: 8px;
      font-size: 15px;
      color: #1e293b;
      background: #f8fafc;
      margin-bottom: 18px;
      outline: none;
      transition: border 0.2s;
    }
    input:focus, textarea:focus, select:focus {
      border-color: #0ea5e9;
      background: white;
    }
    textarea { height: 100px; resize: vertical; }
    .warning {
      background: #fef2f2;
      border: 1.5px solid #fecaca;
      border-radius: 8px;
      padding: 12px 16px;
      font-size: 13px;
      color: #b91c1c;
      margin-bottom: 24px;
      line-height: 1.5;
    }
    button {
      width: 100%;
      padding: 13px;
      background: #ef4444;
      color: white;
      font-size: 15px;
      font-weight: 600;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.2s;
    }
    button:hover { background: #dc2626; }
    button:disabled { background: #94a3b8; cursor: not-allowed; }
    .success {
      display: none;
      text-align: center;
      padding: 20px 0;
    }
    .success-icon { font-size: 48px; margin-bottom: 12px; }
    .success h2 { color: #0c4a6e; margin-bottom: 8px; }
    .success p { color: #64748b; font-size: 14px; line-height: 1.6; }
    .footer {
      margin-top: 24px;
      font-size: 12px;
      color: #94a3b8;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="logo">
      <div class="logo-icon">✝️</div>
      <span class="logo-text">Holy Horizon</span>
    </div>

    <div id="formSection">
      <h1>Delete My Account</h1>
      <p class="subtitle">
        We're sorry to see you go. Submit this form and we will delete your account and all associated data within <strong>30 days</strong>.
      </p>

      <div class="warning">
        ⚠️ This action is <strong>permanent and irreversible</strong>. All your prayer journals, testimonies, habits, quests, and messages will be permanently deleted.
      </div>

      <form id="deleteForm">
        <label for="email">Email Address (used for your account)</label>
        <input type="email" id="email" name="email" placeholder="you@example.com" required />

        <label for="reason">Reason for leaving (optional)</label>
        <select id="reason" name="reason">
          <option value="">Select a reason...</option>
          <option value="no_longer_using">I no longer use the app</option>
          <option value="privacy_concerns">Privacy concerns</option>
          <option value="switching_app">Switching to another app</option>
          <option value="technical_issues">Technical issues</option>
          <option value="other">Other</option>
        </select>

        <label for="message">Additional comments (optional)</label>
        <textarea id="message" name="message" placeholder="Tell us anything else..."></textarea>

        <button type="submit" id="submitBtn">Request Account Deletion</button>
      </form>
    </div>

    <div class="success" id="successSection">
      <div class="success-icon">✅</div>
      <h2>Request Received</h2>
      <p>We've received your account deletion request. Your account and all data will be permanently deleted within <strong>30 days</strong>.<br/><br/>Thank you for being part of Holy Horizon.</p>
    </div>

    <div class="footer">Holy Horizon &bull; Questions? Contact us at <a href="mailto:your-email@example.com" style="color:#0ea5e9;">your-email@example.com</a></div>
  </div>

  <script>
    const form = document.getElementById('deleteForm');

    form.addEventListener('submit', function(e) {
      e.preventDefault();
      const email = document.getElementById('email').value;
      const reason = document.getElementById('reason').value;
      const message = document.getElementById('message').value;

      const body = `Account Deletion Request\n\nEmail: ${email}\nReason: ${reason || 'Not specified'}\nComments: ${message || 'None'}`;
      const mailtoLink = `mailto:your-email@example.com?subject=Account Deletion Request – Holy Horizon&body=${encodeURIComponent(body)}`;

      window.location.href = mailtoLink;

      document.getElementById('formSection').style.display = 'none';
      document.getElementById('successSection').style.display = 'block';
    });
  </script>
</body>
</html>
