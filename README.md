Vulnerability Assessment Report for a Live Website

Overview
This project documents a passive vulnerability assessment performed on a live website (https://www.immuniweb.com/). The audit was conducted on 09 March 2026 by Mkhonta Nhlosenhle.
The goal was to evaluate the security posture of the site using non-intrusive methods and provide actionable recommendations for remediation.

Methodology
The assessment relied on passive observation and configuration review using the following tools:
- Nmap → Basic port exposure analysis
- OWASP ZAP → Passive vulnerability scanning
- Browser DevTools → Header, cookie, and component inspection
- SSL Labs → SSL/TLS configuration testing
Scope: Public-facing pages only. No exploitation or harmful testing was performed.

 Key Findings
High Priority Issues
- Open Port 80 (HTTP) → Unencrypted traffic
- Open Port 8080 → Possible test/admin exposure
- Open Port 8443 → Possible admin console exposure
- Cookies missing HttpOnly flag → Session hijacking risk
Medium Priority Issues
- Open Port 443 (HTTPS) → Needs SSL/TLS hardening (HSTS, cipher review)
- Missing Content-Security-Policy (CSP) header
- Missing HSTS (Strict-Transport-Security)
- Use of third-party scripts (Google Tag Manager, Cloudflare Rocket Loader)
Low Priority Issues
- SSL/TLS configuration rated A+ (excellent)
- No visible outdated components in source code
- Server leaks version information via headers

Risk Prioritization
- High Priority → Fix immediately (1–2 weeks)
- Medium Priority → Address within 1 month
- Low Priority → Monitor and maintain during ongoing reviews

Remediation Roadmap
Immediate (1–2 weeks)
- Redirect HTTP traffic to HTTPS
- Restrict/disable ports 8080 and 8443
- Secure cookies with HttpOnly and Secure flags
Short Term (1 month)
- Enable HSTS
- Add CSP header
- Review third-party script configurations
Ongoing
- Maintain SSL/TLS A+ rating
- Disable server version disclosure
- Conduct quarterly security reviews

Project Structure

1.Vulnerability Assessment Report for a Live Website.pdf 

2.README.md
  
Conclusion

This assessment highlights critical areas where the website can improve its security posture. Addressing high-priority issues first will significantly reduce risk exposure. Continuous monitoring and regular updates are recommended to maintain a strong security baseline.

