<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Monisha Sood – Product Manager</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    :root {
      --primary: #6366f1;
      --primary-light: #818cf8;
      --secondary: #8b5cf6;
      --accent: #ec4899;
      --success: #10b981;
      --dark: #0f172a;
      --dark-surface: #1e293b;
      --light: #f1f5f9;
      --text-primary: #e2e8f0;
      --text-secondary: #cbd5e1;
      --text-muted: #94a3b8;
      --border: rgba(255, 255, 255, 0.1);
    }
    
    html {
      scroll-behavior: smooth;
    }
    
    body {
      font-family: 'Inter', sans-serif;
      background: var(--dark);
      color: var(--light);
      overflow-x: hidden;
      line-height: 1.6;
    }
    
    /* Animated Background */
    .bg-animation {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 0;
      overflow: hidden;
      opacity: 0.6;
    }
    
    .grid-bg {
      position: absolute;
      width: 100%;
      height: 100%;
      background-image: 
        linear-gradient(rgba(99, 102, 241, 0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(99, 102, 241, 0.03) 1px, transparent 1px);
      background-size: 50px 50px;
      animation: gridMove 20s linear infinite;
    }
    
    @keyframes gridMove {
      0% { transform: translate(0, 0); }
      100% { transform: translate(50px, 50px); }
    }
    
    .orb {
      position: absolute;
      border-radius: 50%;
      filter: blur(80px);
      opacity: 0.3;
      animation: float 20s infinite ease-in-out;
    }
    
    .orb1 {
      width: 500px;
      height: 500px;
      background: var(--primary);
      top: -200px;
      left: -200px;
    }
    
    .orb2 {
      width: 400px;
      height: 400px;
      background: var(--secondary);
      bottom: -150px;
      right: -150px;
      animation-delay: 5s;
    }
    
    @keyframes float {
      0%, 100% { transform: translate(0, 0) scale(1); }
      50% { transform: translate(30px, -30px) scale(1.05); }
    }
    
    /* Navigation */
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      padding: 16px 0;
      background: rgba(15, 23, 42, 0.9);
      backdrop-filter: blur(20px);
      z-index: 1000;
      border-bottom: 1px solid var(--border);
    }
    
    nav .container {
      max-width: 1400px;
      margin: 0 auto;
      padding: 0 40px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    
    .logo {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 24px;
      font-weight: 700;
      background: linear-gradient(135deg, var(--primary-light), var(--accent));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    .nav-links {
      display: flex;
      gap: 32px;
      list-style: none;
      align-items: center;
    }
    
    .nav-links a {
      color: var(--text-secondary);
      text-decoration: none;
      font-weight: 500;
      font-size: 14px;
      transition: all 0.3s;
      position: relative;
    }
    
    .nav-links a:hover {
      color: var(--primary-light);
    }
    
    .nav-cta {
      padding: 10px 24px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      border-radius: 8px;
      color: white !important;
      font-weight: 600;
      transition: all 0.3s;
    }
    
    .nav-cta:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(99, 102, 241, 0.4);
    }
    
    /* Container */
    .container {
      max-width: 1400px;
      margin: 0 auto;
      padding: 0 40px;
      position: relative;
      z-index: 1;
    }
    
    /* Hero Section */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding-top: 80px;
    }
    
    .hero-content {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 80px;
      align-items: center;
    }
    
    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 16px;
      background: rgba(99, 102, 241, 0.1);
      border: 1px solid rgba(99, 102, 241, 0.3);
      border-radius: 50px;
      font-size: 13px;
      font-weight: 600;
      color: var(--primary-light);
      margin-bottom: 24px;
      animation: slideInLeft 1s ease-out;
    }
    
    .status-dot {
      width: 8px;
      height: 8px;
      background: var(--success);
      border-radius: 50%;
      animation: pulse 2s infinite;
    }
    
    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.5; }
    }
    
    .hero-text h1 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 64px;
      font-weight: 700;
      line-height: 1.1;
      margin-bottom: 16px;
      color: white;
      animation: slideInLeft 1s ease-out 0.1s backwards;
    }
    
    .hero-text h1 .gradient-text {
      background: linear-gradient(135deg, var(--primary-light), var(--accent));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    .hero-text .subtitle {
      font-size: 22px;
      color: var(--text-secondary);
      margin-bottom: 24px;
      font-weight: 500;
      animation: slideInLeft 1s ease-out 0.2s backwards;
    }
    
    .hero-text p {
      font-size: 17px;
      line-height: 1.7;
      color: var(--text-primary);
      margin-bottom: 32px;
      animation: slideInLeft 1s ease-out 0.3s backwards;
    }
    
    @keyframes slideInLeft {
      from {
        opacity: 0;
        transform: translateX(-30px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }
    
    .cta-buttons {
      display: flex;
      gap: 16px;
      animation: slideInLeft 1s ease-out 0.4s backwards;
      flex-wrap: wrap;
    }
    
    .btn {
      padding: 14px 28px;
      border-radius: 10px;
      font-weight: 600;
      font-size: 15px;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: all 0.3s;
      cursor: pointer;
    }
    
    .btn-primary {
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      color: white;
      box-shadow: 0 8px 24px rgba(99, 102, 241, 0.3);
    }
    
    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 32px rgba(99, 102, 241, 0.4);
    }
    
    .btn-secondary {
      background: var(--dark-surface);
      color: white;
      border: 1px solid var(--border);
    }
    
    .btn-secondary:hover {
      background: rgba(255, 255, 255, 0.08);
      border-color: var(--primary);
      transform: translateY(-2px);
    }
    
    /* Metrics Dashboard in Hero */
    .hero-metrics {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 16px;
      animation: slideInRight 1s ease-out 0.5s backwards;
    }
    
    @keyframes slideInRight {
      from {
        opacity: 0;
        transform: translateX(30px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }
    
    .metric-card {
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(10px);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 24px;
      transition: all 0.3s;
      position: relative;
      overflow: hidden;
    }
    
    .metric-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 3px;
      background: linear-gradient(90deg, var(--primary), var(--accent));
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.5s;
    }
    
    .metric-card:hover::before {
      transform: scaleX(1);
    }
    
    .metric-card:hover {
      background: rgba(255, 255, 255, 0.06);
      border-color: var(--primary);
      transform: translateY(-4px);
    }
    
    .metric-value {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 36px;
      font-weight: 700;
      background: linear-gradient(135deg, var(--primary-light), var(--accent));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 8px;
    }
    
    .metric-label {
      color: var(--text-secondary);
      font-size: 13px;
      font-weight: 500;
    }
    
    .metric-change {
      display: inline-flex;
      align-items: center;
      gap: 4px;
      margin-top: 8px;
      padding: 4px 8px;
      background: rgba(16, 185, 129, 0.1);
      border-radius: 6px;
      font-size: 12px;
      font-weight: 600;
      color: var(--success);
    }
    
    /* Profile Picture Section */
    .hero-profile {
      position: relative;
      animation: slideInRight 1s ease-out 0.5s backwards;
    }
    
    .profile-card {
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(10px);
      border: 1px solid var(--border);
      border-radius: 24px;
      padding: 32px;
      text-align: center;
      transition: all 0.4s;
    }
    
    .profile-card:hover {
      border-color: var(--primary);
      transform: translateY(-8px);
      box-shadow: 0 20px 60px rgba(99, 102, 241, 0.3);
    }
    
    .profile-image-container {
      position: relative;
      width: 280px;
      height: 280px;
      margin: 0 auto 24px;
    }
    
    .profile-image-bg {
      position: absolute;
      inset: -8px;
      background: linear-gradient(135deg, var(--primary), var(--accent));
      border-radius: 50%;
      animation: rotate 8s linear infinite;
      opacity: 0.5;
    }
    
    @keyframes rotate {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }
    
    .profile-image {
      position: relative;
      width: 100%;
      height: 100%;
      border-radius: 50%;
      object-fit: cover;
      border: 4px solid var(--dark);
      box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
    }
    
    .profile-name {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 24px;
      font-weight: 700;
      color: white;
      margin-bottom: 8px;
    }
    
    .profile-title {
      color: var(--text-secondary);
      font-size: 14px;
      font-weight: 500;
      margin-bottom: 24px;
      padding-bottom: 24px;
      border-bottom: 1px solid var(--border);
    }
    
    .profile-links {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    
    .profile-link {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 12px 20px;
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid var(--border);
      border-radius: 10px;
      color: var(--text-primary);
      text-decoration: none;
      font-size: 14px;
      font-weight: 600;
      transition: all 0.3s;
    }
    
    .profile-link:hover {
      background: rgba(99, 102, 241, 0.15);
      border-color: var(--primary);
      transform: translateX(4px);
    }
    
    .profile-link.primary {
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      border-color: transparent;
      color: white;
    }
    
    .profile-link.primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(99, 102, 241, 0.4);
    }
    
    .link-icon {
      font-size: 18px;
      color: var(--primary-light);
      font-weight: 400;
    }
    
    /* LinkedIn Icon SVG */
    .linkedin-icon {
      width: 18px;
      height: 18px;
      fill: currentColor;
    }
    
    .social-link .linkedin-icon {
      width: 20px;
      height: 20px;
    }
    
    /* Section */
    section {
      padding: 120px 0;
      position: relative;
    }
    
    .section-header {
      text-align: center;
      margin-bottom: 80px;
    }
    
    .section-tag {
      display: inline-block;
      padding: 6px 16px;
      background: rgba(99, 102, 241, 0.1);
      border: 1px solid rgba(99, 102, 241, 0.3);
      border-radius: 50px;
      color: var(--primary-light);
      font-size: 12px;
      font-weight: 700;
      letter-spacing: 0.5px;
      text-transform: uppercase;
      margin-bottom: 16px;
    }
    
    .section-title {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 48px;
      font-weight: 700;
      margin-bottom: 16px;
      color: white;
    }
    
    .section-description {
      font-size: 18px;
      color: var(--text-secondary);
      max-width: 700px;
      margin: 0 auto;
      line-height: 1.7;
    }
    
    /* Product Case Studies - NEW */
    .case-studies {
      display: grid;
      gap: 40px;
    }
    
    .case-study {
      background: rgba(255, 255, 255, 0.03);
      backdrop-filter: blur(10px);
      border: 1px solid var(--border);
      border-radius: 24px;
      overflow: hidden;
      transition: all 0.4s;
      position: relative;
    }
    
    .case-study:hover {
      border-color: var(--primary);
      transform: translateY(-8px);
      box-shadow: 0 20px 60px rgba(99, 102, 241, 0.2);
    }
    
    .case-study-header {
      padding: 40px 40px 0;
    }
    
    .case-study-meta {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 24px;
    }
    
    .company-tag {
      padding: 6px 14px;
      background: rgba(99, 102, 241, 0.15);
      border: 1px solid rgba(99, 102, 241, 0.3);
      border-radius: 8px;
      font-size: 13px;
      font-weight: 600;
      color: var(--primary-light);
    }
    
    .timeline {
      color: var(--text-muted);
      font-size: 13px;
      font-weight: 500;
    }
    
    .case-study h3 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 32px;
      font-weight: 700;
      color: white;
      margin-bottom: 16px;
      line-height: 1.3;
    }
    
    .case-study-intro {
      color: var(--text-secondary);
      font-size: 16px;
      line-height: 1.7;
      margin-bottom: 32px;
    }
    
    .case-study-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
      padding: 0 40px 40px;
    }
    
    .case-section h4 {
      font-size: 14px;
      font-weight: 700;
      color: var(--primary-light);
      text-transform: uppercase;
      letter-spacing: 0.5px;
      margin-bottom: 16px;
    }
    
    .problem-statement {
      background: rgba(236, 72, 153, 0.08);
      border-left: 3px solid var(--accent);
      padding: 20px;
      border-radius: 8px;
      margin-bottom: 24px;
    }
    
    .problem-statement p {
      color: var(--text-primary);
      font-size: 15px;
      line-height: 1.6;
      margin: 0;
    }
    
    .solution-list {
      list-style: none;
      padding: 0;
    }
    
    .solution-list li {
      color: var(--text-primary);
      font-size: 15px;
      line-height: 1.6;
      margin-bottom: 12px;
      padding-left: 24px;
      position: relative;
    }
    
    .solution-list li::before {
      content: '→';
      position: absolute;
      left: 0;
      color: var(--primary-light);
      font-weight: bold;
    }
    
    .impact-metrics {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 16px;
      margin-top: 24px;
    }
    
    .impact-card {
      background: rgba(16, 185, 129, 0.08);
      border: 1px solid rgba(16, 185, 129, 0.2);
      border-radius: 12px;
      padding: 16px;
      text-align: center;
    }
    
    .impact-number {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 28px;
      font-weight: 700;
      color: var(--success);
      margin-bottom: 4px;
    }
    
    .impact-label {
      font-size: 12px;
      color: var(--text-secondary);
      font-weight: 500;
    }
    
    .tools-used {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 16px;
    }
    
    .tool-badge {
      padding: 6px 12px;
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid var(--border);
      border-radius: 6px;
      font-size: 12px;
      font-weight: 600;
      color: var(--text-secondary);
    }
    
    /* PM Principles - NEW */
    .principles-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
      margin-top: 60px;
    }
    
    .principle-card {
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 32px;
      transition: all 0.3s;
      position: relative;
      overflow: hidden;
    }
    
    .principle-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, var(--primary) 0%, transparent 70%);
      opacity: 0;
      transition: opacity 0.3s;
    }
    
    .principle-card:hover {
      border-color: var(--primary);
      transform: translateY(-4px);
    }
    
    .principle-card:hover::before {
      opacity: 0.08;
    }
    
    .principle-icon {
      font-size: 40px;
      margin-bottom: 20px;
      position: relative;
      z-index: 1;
      font-weight: 300;
      color: var(--primary-light);
      text-shadow: 0 0 20px rgba(99, 102, 241, 0.5);
    }
    
    .principle-card h3 {
      font-size: 20px;
      font-weight: 600;
      color: white;
      margin-bottom: 12px;
      position: relative;
      z-index: 1;
    }
    
    .principle-card p {
      color: var(--text-secondary);
      font-size: 14px;
      line-height: 1.6;
      position: relative;
      z-index: 1;
    }
    
    /* Skills Section - Modernized */
    .skills-categories {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 24px;
    }
    
    .skill-category {
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 32px;
      transition: all 0.3s;
    }
    
    .skill-category:hover {
      border-color: var(--primary);
      background: rgba(255, 255, 255, 0.05);
    }
    
    .skill-category h3 {
      font-size: 20px;
      font-weight: 600;
      color: white;
      margin-bottom: 20px;
      display: flex;
      align-items: center;
      gap: 12px;
    }
    
    .skill-category h3::before {
      content: '';
      width: 4px;
      height: 24px;
      background: linear-gradient(180deg, var(--primary), var(--accent));
      border-radius: 2px;
    }
    
    .skill-items {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }
    
    .skill-item {
      padding: 8px 16px;
      background: rgba(99, 102, 241, 0.1);
      border: 1px solid rgba(99, 102, 241, 0.2);
      border-radius: 8px;
      font-size: 13px;
      font-weight: 500;
      color: var(--text-primary);
      transition: all 0.3s;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
    }
    
    .skill-item:hover {
      background: rgba(99, 102, 241, 0.2);
      border-color: var(--primary);
      transform: translateY(-2px);
    }
    
    /* Certification links - clickable ones have extra styling */
    a.skill-item {
      position: relative;
    }
    
    a.skill-item::after {
      content: '↗';
      margin-left: 6px;
      font-size: 11px;
      opacity: 0;
      transition: opacity 0.3s;
    }
    
    a.skill-item:hover::after {
      opacity: 1;
    }
    
    /* Awards - Redesigned */
    .awards-showcase {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }
    
    .award-card-modern {
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 32px;
      text-align: center;
      transition: all 0.3s;
      position: relative;
      overflow: hidden;
    }
    
    .award-card-modern::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, var(--accent) 0%, transparent 70%);
      opacity: 0;
      transition: opacity 0.3s;
    }
    
    .award-card-modern:hover {
      border-color: var(--accent);
      transform: translateY(-6px);
    }
    
    .award-card-modern:hover::before {
      opacity: 0.1;
    }
    
    .award-icon-modern {
      font-size: 48px;
      margin-bottom: 16px;
      position: relative;
      z-index: 1;
      font-weight: 300;
      color: var(--accent);
      text-shadow: 0 0 20px rgba(236, 72, 153, 0.5);
    }
    
    .award-card-modern h3 {
      font-size: 18px;
      font-weight: 600;
      color: white;
      margin-bottom: 12px;
      position: relative;
      z-index: 1;
    }
    
    .award-card-modern p {
      color: var(--text-secondary);
      font-size: 14px;
      line-height: 1.6;
      position: relative;
      z-index: 1;
    }
    
    /* Footer */
    footer {
      background: rgba(15, 23, 42, 0.95);
      backdrop-filter: blur(20px);
      border-top: 1px solid var(--border);
      padding: 60px 0 30px;
      margin-top: 120px;
    }
    
    .footer-content {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 60px;
      margin-bottom: 40px;
    }
    
    .footer-brand h3 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 24px;
      margin-bottom: 12px;
      background: linear-gradient(135deg, var(--primary-light), var(--accent));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    .footer-brand p {
      color: var(--text-secondary);
      line-height: 1.6;
      font-size: 14px;
      margin-bottom: 20px;
    }
    
    .social-links {
      display: flex;
      gap: 12px;
    }
    
    .social-link {
      width: 40px;
      height: 40px;
      border-radius: 10px;
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid var(--border);
      display: flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      font-size: 18px;
      transition: all 0.3s;
    }
    
    .social-link:hover {
      background: var(--primary);
      border-color: var(--primary);
      transform: translateY(-3px);
    }
    
    .footer-section h4 {
      font-size: 14px;
      font-weight: 600;
      color: white;
      margin-bottom: 16px;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }
    
    .footer-section ul {
      list-style: none;
    }
    
    .footer-section a {
      color: var(--text-secondary);
      text-decoration: none;
      display: block;
      margin-bottom: 10px;
      font-size: 14px;
      transition: color 0.3s;
    }
    
    .footer-section a:hover {
      color: var(--primary-light);
    }
    
    .footer-bottom {
      text-align: center;
      padding-top: 30px;
      border-top: 1px solid var(--border);
      color: var(--text-muted);
      font-size: 13px;
    }
    
    /* Scroll to top */
    .scroll-top {
      position: fixed;
      bottom: 30px;
      right: 30px;
      width: 50px;
      height: 50px;
      border-radius: 12px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      font-size: 24px;
      box-shadow: 0 8px 24px rgba(99, 102, 241, 0.4);
      transition: all 0.3s;
      z-index: 999;
      opacity: 0;
      pointer-events: none;
    }
    
    .scroll-top.visible {
      opacity: 1;
      pointer-events: all;
    }
    
    .scroll-top:hover {
      transform: translateY(-4px);
      box-shadow: 0 12px 32px rgba(99, 102, 241, 0.5);
    }
    
    /* Responsive */
    @media (max-width: 1024px) {
      .hero-content {
        grid-template-columns: 1fr;
        gap: 60px;
      }
      
      .profile-image-container {
        width: 220px;
        height: 220px;
      }
      
      .hero-metrics {
        grid-template-columns: repeat(2, 1fr);
      }
      
      .case-study-grid {
        grid-template-columns: 1fr;
      }
      
      .principles-grid {
        grid-template-columns: 1fr;
      }
      
      .skills-categories {
        grid-template-columns: 1fr;
      }
      
      .awards-showcase {
        grid-template-columns: 1fr;
      }
      
      .footer-content {
        grid-template-columns: 1fr;
        gap: 40px;
      }
    }
    
    @media (max-width: 768px) {
      .container {
        padding: 0 20px;
      }
      
      section {
        padding: 80px 0;
      }
      
      .hero-text h1 {
        font-size: 42px;
      }
      
      .section-title {
        font-size: 36px;
      }
      
      .nav-links {
        display: none;
      }
      
      .hero-metrics {
        grid-template-columns: 1fr;
      }
      
      .metric-card {
        padding: 20px;
      }
      
      .case-study h3 {
        font-size: 24px;
      }
      
      .case-study-header,
      .case-study-grid {
        padding: 24px;
      }
    }
    
    /* Interactive Animation Keyframes */
    @keyframes float-particle {
      0% {
        opacity: 0;
        transform: translateY(0) scale(0);
      }
      50% {
        opacity: 0.8;
      }
      100% {
        opacity: 0;
        transform: translateY(-100px) scale(1);
      }
    }
    
    @keyframes ripple {
      to {
        transform: scale(4);
        opacity: 0;
      }
    }
    
    @keyframes glow {
      0%, 100% {
        box-shadow: 0 0 20px rgba(99, 102, 241, 0.5);
      }
      50% {
        box-shadow: 0 0 40px rgba(99, 102, 241, 0.8);
      }
    }
    
    /* Cursor trail effect */
    .cursor-trail {
      position: fixed;
      width: 8px;
      height: 8px;
      background: var(--primary-light);
      border-radius: 50%;
      pointer-events: none;
      opacity: 0.6;
      z-index: 9999;
      animation: fade-out 1s forwards;
    }
    
    @keyframes fade-out {
      to {
        opacity: 0;
        transform: scale(2);
      }
    }
    
    /* Gradient text animation */
    .gradient-text {
      background: linear-gradient(
        90deg,
        var(--primary-light),
        var(--accent),
        var(--secondary),
        var(--primary-light)
      );
      background-size: 200% auto;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      animation: gradient-shift 3s linear infinite;
      display: inline-block;
      min-width: 200px;
    }
    
    @keyframes gradient-shift {
      0% {
        background-position: 0% center;
      }
      100% {
        background-position: 200% center;
      }
    }
    
    /* Hover state for cards with 3D effect */
    .case-study:hover,
    .principle-card:hover,
    .award-card-modern:hover {
      transform: translateY(-8px) scale(1.02);
      box-shadow: 0 25px 70px rgba(99, 102, 241, 0.3);
    }
    
    /* Pulse animation for status dot */
    @keyframes pulse {
      0%, 100% {
        opacity: 1;
        transform: scale(1);
      }
      50% {
        opacity: 0.5;
        transform: scale(1.2);
      }
    }
    
    /* Shake animation for CTAs */
    @keyframes shake {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-5px); }
      75% { transform: translateX(5px); }
    }
    
    .btn:active {
      animation: shake 0.3s;
    }
    
    /* Interactive metric cards */
    .metric-card {
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .metric-card:active {
      transform: scale(0.95);
    }
    
    /* Profile image zoom on hover */
    .profile-image {
      transition: transform 0.5s ease;
    }
    
    .profile-image-container:hover .profile-image {
      transform: scale(1.05);
    }
    
    /* Smooth color transitions */
    * {
      transition: color 0.3s ease, background-color 0.3s ease, border-color 0.3s ease;
    }
  </style>
</head>
<body>
  <!-- Animated Background -->
  <div class="bg-animation">
    <div class="grid-bg"></div>
    <div class="orb orb1"></div>
    <div class="orb orb2"></div>
  </div>

  <!-- Navigation -->
  <nav>
    <div class="container">
      <div class="logo">MS</div>
      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#case-studies">Case Studies</a></li>
        <li><a href="#principles">Approach</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#awards">Recognition</a></li>
        <li><a href="#contact" class="nav-cta">Get in Touch</a></li>
      </ul>
    </div>
  </nav>

  <!-- Hero Section -->
  <section id="home" class="hero">
    <div class="container">
      <div class="hero-content">
        <div class="hero-text">
          <div class="hero-badge">
            <span class="status-dot"></span>
            Open to PM Opportunities
          </div>
          <h1>Building products that <span class="gradient-text">drive impact</span></h1>
          <p class="subtitle">Product Manager | MBA '26 | Data-Driven Strategist</p>
          <p>I transform complex challenges into elegant solutions through user-centered design, data-driven strategy, and cross-functional collaboration. With 6+ years leading product initiatives from 0→1, I've driven $50M+ in business value and built systems that scale.</p>
          <div class="cta-buttons">
            <a href="#case-studies" class="btn btn-primary">
              View Case Studies →
            </a>
            <a href="Monisha_Sood_Resume.pdf" class="btn btn-secondary" download>
              Download Resume
            </a>
            <a href="https://www.linkedin.com/in/monishasood07/" class="btn btn-secondary" target="_blank">
              <svg class="linkedin-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
              LinkedIn
            </a>
          </div>
        </div>
        
        <div class="hero-profile">
          <div class="profile-card">
            <div class="profile-image-container">
              <div class="profile-image-bg"></div>
              <img src="monisha-profile.png" alt="Monisha Sood" class="profile-image">
            </div>
            <h3 class="profile-name">Monisha Sood</h3>
            <p class="profile-title">Product Manager | MBA '26</p>
            <div class="profile-links">
              <a href="Monisha_Sood_Resume.pdf" class="profile-link primary" download>
                <span class="link-icon">▣</span>
                Download Resume
              </a>
              <a href="https://www.linkedin.com/in/monishasood07/" class="profile-link" target="_blank">
                <svg class="linkedin-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                </svg>
                LinkedIn Profile
              </a>
              <a href="mailto:monisha.sood@wisc.edu" class="profile-link">
                <span class="link-icon">✉</span>
                monisha.sood@wisc.edu
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="hero-metrics">
          <div class="metric-card">
            <div class="metric-value">6+</div>
            <div class="metric-label">Years in Product</div>
            <div class="metric-change">↑ Growing</div>
          </div>
          <div class="metric-card">
            <div class="metric-value">$50M+</div>
            <div class="metric-label">Value Created</div>
            <div class="metric-change">↑ Contracts Closed</div>
          </div>
          <div class="metric-card">
            <div class="metric-value">70%</div>
            <div class="metric-label">Efficiency Gains</div>
            <div class="metric-change">↑ Through Automation</div>
          </div>
          <div class="metric-card">
            <div class="metric-value">3</div>
            <div class="metric-label">MVPs Launched</div>
            <div class="metric-change">↑ 0→1 Products</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Product Case Studies Section -->
  <section id="case-studies">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">PRODUCT WORK</span>
        <h2 class="section-title">Featured Case Studies</h2>
        <p class="section-description">
          Real product problems. Data-driven solutions. Measurable impact.
        </p>
      </div>
      
      <div class="case-studies">
        <!-- Case Study 1: SecondWind NIL Platform -->
        <div class="case-study">
          <div class="case-study-header">
            <div class="case-study-meta">
              <span class="company-tag">SecondWind Pro</span>
              <span class="timeline">Jun 2025 – Present</span>
            </div>
            <h3>Building NIL Valuation Platform from Zero</h3>
            <p class="case-study-intro">
              Led the 0→1 development of an AI-powered platform connecting Division 1 athletes with NIL opportunities, coordinating cross-functional teams to deliver an MVP that enabled $500K+ in fundraising within the first month.
            </p>
          </div>
          
          <div class="case-study-grid">
            <div class="case-section">
              <h4>The Challenge</h4>
              <div class="problem-statement">
                <p>College athletes needed a trusted platform to showcase their NIL value, while donors and collectives lacked data-driven tools to identify and evaluate talent across 100+ schools. Manual outreach was eating 80% of the team's time.</p>
              </div>
              
              <h4>My Approach</h4>
              <ul class="solution-list">
                <li>Conducted user interviews with 15+ athletes, donors, and collectives to validate product-market fit</li>
                <li>Designed product roadmap prioritizing verified profiles and automated outreach</li>
                <li>Built cross-functional team of 8 (engineering, data, fundraising) with clear OKRs</li>
                <li>Architected Airtable/Zapier automation reducing manual work by 70%</li>
                <li>Led weekly leadership standups to maintain velocity and alignment</li>
              </ul>
            </div>
            
            <div class="case-section">
              <h4>Impact Delivered</h4>
              <div class="impact-metrics">
                <div class="impact-card">
                  <div class="impact-number">25+</div>
                  <div class="impact-label">Athletes Onboarded (Month 1)</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">$500K+</div>
                  <div class="impact-label">Fundraising Supported</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">70%</div>
                  <div class="impact-label">Time Saved via Automation</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">40%</div>
                  <div class="impact-label">Faster Team Delivery</div>
                </div>
              </div>
              
              <h4>Key Learnings</h4>
              <ul class="solution-list">
                <li><strong>Start with the problem:</strong> User research uncovered that trust & verification mattered more than fancy features</li>
                <li><strong>Automate ruthlessly:</strong> Building scalable systems early enabled us to punch above our weight</li>
                <li><strong>Cross-functional = competitive advantage:</strong> Breaking down silos between teams accelerated every decision</li>
              </ul>
              
              <div class="tools-used">
                <span class="tool-badge">Airtable</span>
                <span class="tool-badge">Zapier</span>
                <span class="tool-badge">User Research</span>
                <span class="tool-badge">OKRs</span>
                <span class="tool-badge">Agile</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Case Study 2: Flyhomes Sales Compensation -->
        <div class="case-study">
          <div class="case-study-header">
            <div class="case-study-meta">
              <span class="company-tag">Flyhomes</span>
              <span class="timeline">Jun 2023 – Jun 2024</span>
            </div>
            <h3>Redesigning Sales Compensation to Save $48MM</h3>
            <p class="case-study-intro">
              Transformed a broken compensation system through data analysis and stakeholder alignment, migrating 100+ users to a new platform while maintaining 95% satisfaction and unlocking massive cost savings.
            </p>
          </div>
          
          <div class="case-study-grid">
            <div class="case-section">
              <h4>The Challenge</h4>
              <div class="problem-statement">
                <p>Sales team was demotivated by opaque compensation plans. Manual processing errors created mistrust. Company needed to optimize variable incentives without losing top performers.</p>
              </div>
              
              <h4>My Approach</h4>
              <ul class="solution-list">
                <li>Analyzed performance data for 200+ agents to identify compensation optimization opportunities</li>
                <li>Partnered with finance & engineering to redesign system architecture</li>
                <li>Led cross-functional migration with zero downtime for $600K in processed commissions</li>
                <li>Created training program onboarding 50+ associates in 3 days</li>
                <li>Built Airtable dashboards for real-time performance tracking</li>
              </ul>
            </div>
            
            <div class="case-section">
              <h4>Impact Delivered</h4>
              <div class="impact-metrics">
                <div class="impact-card">
                  <div class="impact-number">$48MM</div>
                  <div class="impact-label">Cost Savings Achieved</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">95%</div>
                  <div class="impact-label">Agent Satisfaction Rate</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">17%</div>
                  <div class="impact-label">CSAT Improvement</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">28%</div>
                  <div class="impact-label">Team Effectiveness Boost</div>
                </div>
              </div>
              
              <h4>Key Learnings</h4>
              <ul class="solution-list">
                <li><strong>Stakeholder buy-in is everything:</strong> Transparent communication turned skeptics into champions</li>
                <li><strong>Data drives decisions:</strong> Analytics revealed insights that intuition missed</li>
                <li><strong>Change management matters:</strong> Technical excellence means nothing if users don't adopt</li>
              </ul>
              
              <div class="tools-used">
                <span class="tool-badge">Data Analysis</span>
                <span class="tool-badge">Airtable</span>
                <span class="tool-badge">Change Management</span>
                <span class="tool-badge">SQL</span>
                <span class="tool-badge">Stakeholder Alignment</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Case Study 3: Flyhomes Product Development -->
        <div class="case-study">
          <div class="case-study-header">
            <div class="case-study-meta">
              <span class="company-tag">Flyhomes</span>
              <span class="timeline">Apr 2022 – Jun 2023</span>
            </div>
            <h3>Accelerating Product Velocity Through Agile Transformation</h3>
            <p class="case-study-intro">
              Transformed product development process from waterfall to agile, leading end-to-end initiatives that improved team efficiency 68% and customer satisfaction 32% through rapid iteration and data-driven prioritization.
            </p>
          </div>
          
          <div class="case-study-grid">
            <div class="case-section">
              <h4>The Challenge</h4>
              <div class="problem-statement">
                <p>Product releases were slow and buggy. Teams worked in silos. Customer feedback loop was broken. SLAs were consistently missed, eroding trust with clients.</p>
              </div>
              
              <h4>My Approach</h4>
              <ul class="solution-list">
                <li>Implemented agile ceremonies (sprint planning, retrospectives, daily standups)</li>
                <li>Created user story framework tied to customer pain points</li>
                <li>Built SQL dashboards for real-time KPI tracking and decision-making</li>
                <li>Established cross-functional testing protocols reducing bugs 40%</li>
                <li>Led product inspections with clients for continuous feedback</li>
              </ul>
            </div>
            
            <div class="case-section">
              <h4>Impact Delivered</h4>
              <div class="impact-metrics">
                <div class="impact-card">
                  <div class="impact-number">68%</div>
                  <div class="impact-label">Team Efficiency Gain</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">32%</div>
                  <div class="impact-label">CSAT Increase</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">20%</div>
                  <div class="impact-label">Faster Delivery</div>
                </div>
                <div class="impact-card">
                  <div class="impact-number">8%</div>
                  <div class="impact-label">SLA Reduction</div>
                </div>
              </div>
              
              <h4>Key Learnings</h4>
              <ul class="solution-list">
                <li><strong>Process enables innovation:</strong> The right framework unlocks creativity rather than constraining it</li>
                <li><strong>Measure what matters:</strong> KPIs aligned teams around shared goals</li>
                <li><strong>Customer proximity wins:</strong> Regular feedback loops shortened the path to product-market fit</li>
              </ul>
              
              <div class="tools-used">
                <span class="tool-badge">Agile/Scrum</span>
                <span class="tool-badge">JIRA</span>
                <span class="tool-badge">SQL</span>
                <span class="tool-badge">User Stories</span>
                <span class="tool-badge">Cross-functional Testing</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PM Principles Section -->
  <section id="principles">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">MY APPROACH</span>
        <h2 class="section-title">Product Philosophy</h2>
        <p class="section-description">
          How I think about building products that matter
        </p>
      </div>
      
      <div class="principles-grid">
        <div class="principle-card">
          <div class="principle-icon">◉</div>
          <h3>Start with the Problem</h3>
          <p>Great products emerge from deep customer understanding, not feature lists. I invest heavily in user research, qualitative feedback, and data analysis before writing a single user story.</p>
        </div>
        
        <div class="principle-card">
          <div class="principle-icon">◈</div>
          <h3>Let Data Drive Decisions</h3>
          <p>Opinions are cheap. Data is truth. I build dashboards, run A/B tests, and define clear metrics to validate assumptions and measure impact at every stage.</p>
        </div>
        
        <div class="principle-card">
          <div class="principle-icon">⚡</div>
          <h3>Ship Fast, Learn Faster</h3>
          <p>MVPs beat perfection every time. I prioritize ruthlessly, cut scope aggressively, and iterate based on real user behavior rather than hypothetical requirements.</p>
        </div>
        
        <div class="principle-card">
          <div class="principle-icon">◆</div>
          <h3>Cross-functional is Non-negotiable</h3>
          <p>Product managers are multipliers, not individual contributors. I build bridges between engineering, design, and business stakeholders to align everyone around shared goals.</p>
        </div>
        
        <div class="principle-card">
          <div class="principle-icon">⚙</div>
          <h3>Automate the Boring Stuff</h3>
          <p>Manual processes are technical debt. I build systems that scale, using tools like Zapier and Airtable to eliminate repetitive work and free teams to focus on what matters.</p>
        </div>
        
        <div class="principle-card">
          <div class="principle-icon">◎</div>
          <h3>Empathy + Execution</h3>
          <p>The best PMs balance vision with pragmatism. I care deeply about user problems while staying ruthlessly focused on delivering tangible business outcomes.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Skills Section -->
  <section id="skills">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">CAPABILITIES</span>
        <h2 class="section-title">Product Management Toolkit</h2>
        <p class="section-description">
          Technical skills and methodologies I use to ship great products
        </p>
      </div>
      
      <div class="skills-categories">
        <div class="skill-category" data-category="strategy">
          <h3>Product Strategy</h3>
          <div class="skill-items">
            <span class="skill-item">Roadmap Planning</span>
            <span class="skill-item">Prioritization Frameworks</span>
            <span class="skill-item">Competitive Analysis</span>
            <span class="skill-item">0→1 MVP Development</span>
            <span class="skill-item">Go-to-Market Strategy</span>
            <span class="skill-item">User Research</span>
            <span class="skill-item">OKR Definition</span>
            <span class="skill-item">Market Sizing</span>
          </div>
        </div>
        
        <div class="skill-category" data-category="execution">
          <h3>Execution & Delivery</h3>
          <div class="skill-items">
            <span class="skill-item">Agile/Scrum</span>
            <span class="skill-item">User Story Writing</span>
            <span class="skill-item">Sprint Planning</span>
            <span class="skill-item">JIRA</span>
            <span class="skill-item">Confluence</span>
            <span class="skill-item">Backlog Management</span>
            <span class="skill-item">Cross-functional Leadership</span>
            <span class="skill-item">Stakeholder Management</span>
          </div>
        </div>
        
        <div class="skill-category" data-category="data">
          <h3>Data & Analytics</h3>
          <div class="skill-items">
            <span class="skill-item">SQL</span>
            <span class="skill-item">Power BI</span>
            <span class="skill-item">A/B Testing</span>
            <span class="skill-item">KPI Tracking</span>
            <span class="skill-item">Data Studio</span>
            <span class="skill-item">R</span>
            <span class="skill-item">Excel Advanced</span>
            <span class="skill-item">Metrics-Driven Decisions</span>
          </div>
        </div>
        
        <div class="skill-category" data-category="tools">
          <h3>Tools & Technical</h3>
          <div class="skill-items">
            <span class="skill-item">Figma</span>
            <span class="skill-item">Airtable</span>
            <span class="skill-item">Zapier</span>
            <span class="skill-item">Salesforce</span>
            <span class="skill-item">Asana</span>
            <span class="skill-item">Lucidchart</span>
            <span class="skill-item">HTML/CSS</span>
            <span class="skill-item">GitHub</span>
            <span class="skill-item">API Integration</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Awards Section -->
  <section id="awards">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">RECOGNITION</span>
        <h2 class="section-title">Awards & Impact</h2>
        <p class="section-description">
          Recognized for driving measurable business outcomes
        </p>
      </div>
      
      <div class="awards-showcase">
        <div class="award-card-modern">
          <div class="award-icon-modern">★</div>
          <h3>Most Trusted Partner</h3>
          <p>Honored for closing $10M+ in contracts and building exceptional client relationships at Flyhomes</p>
        </div>
        
        <div class="award-card-modern">
          <div class="award-icon-modern">◆</div>
          <h3>Superstar of the Month</h3>
          <p>Awarded for 30% productivity improvement and exceeding targets through process innovation</p>
        </div>
        
        <div class="award-card-modern">
          <div class="award-icon-modern">▲</div>
          <h3>Product Impact Champion</h3>
          <p>Recognized for MVP launch that boosted engagement and reduced manual work by 70%</p>
        </div>
      </div>
      
      <div class="section-header" style="margin-top: 80px;">
        <span class="section-tag">CERTIFICATIONS</span>
        <h2 class="section-title">Continuous Learning</h2>
      </div>
      
      <div class="skills-categories">
        <div class="skill-category">
          <h3>Product & Business</h3>
          <div class="skill-items">
            <a href="https://www.linkedin.com/learning/certificates/09a40c572ed115277cb7759589f5a511c715e14866b1364ca31138c49f81b30e" target="_blank" class="skill-item">Product Management (LinkedIn Learning)</a>
            <a href="https://www.udemy.com/certificate/UC-b1173594-700d-442f-a0c6-0208bcc2eacf/" target="_blank" class="skill-item">Product Management (Udemy)</a>
            <span class="skill-item">Business Management (London Business School)</span>
            <a href="https://www.linkedin.com/learning/certificates/d42b50e3f296dd20559c78e9c5d141aa841d1d88f41d31d50d2d4dcf96427785" target="_blank" class="skill-item">Generative AI for Product Managers</a>
            <span class="skill-item">Six Sigma</span>
          </div>
        </div>
        
        <div class="skill-category">
          <h3>Technical & Analytics</h3>
          <div class="skill-items">
            <a href="https://udemy-certificate.s3.amazonaws.com/image/UC-e1d0cada-6bfe-4abf-a3fb-9635d4085bc6.jpg" target="_blank" class="skill-item">SQL Certification (Udemy)</a>
            <a href="https://www.udemy.com/certificate/UC-ec5926b4-c7d7-420f-92e6-49c07f705b34/" target="_blank" class="skill-item">Power BI (Udemy)</a>
            <span class="skill-item">Microsoft Certified Dashboard Training</span>
            <a href="https://www.linkedin.com/learning/certificates/26253a7a429260747c3222960f941254354825bcf67e47a7dd0bc896bcbeb741" target="_blank" class="skill-item">MS Excel Advanced (LinkedIn Learning)</a>
            <span class="skill-item">Data Analysis</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer id="contact">
    <div class="container">
      <div class="footer-content">
        <div class="footer-brand">
          <h3>Monisha Sood</h3>
          <p>Product Manager passionate about solving hard problems with elegant solutions. Currently pursuing my MBA at Wisconsin School of Business while building products that scale.</p>
          <div class="social-links">
            <a href="https://www.linkedin.com/in/monishasood07/" class="social-link" target="_blank" title="LinkedIn">
              <svg class="linkedin-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
            </a>
            <a href="mailto:monisha.sood@wisc.edu" class="social-link" title="Email">✉</a>
            <a href="Monisha_Sood_Resume.pdf" class="social-link" download title="Resume">▣</a>
          </div>
        </div>
        
        <div class="footer-section">
          <h4>Navigation</h4>
          <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#case-studies">Case Studies</a></li>
            <li><a href="#principles">Approach</a></li>
            <li><a href="#skills">Skills</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>Contact</h4>
          <ul>
            <li><a href="mailto:monisha.sood@wisc.edu">monisha.sood@wisc.edu</a></li>
            <li><a href="tel:+16086587795">(608) 658-7795</a></li>
            <li><a href="https://www.linkedin.com/in/monishasood07/" target="_blank">LinkedIn</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>Education</h4>
          <ul>
            <li><a href="https://business.wisc.edu/" target="_blank">UW-Madison MBA '26</a></li>
            <li>Tech Strategy & Product Management</li>
          </ul>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>© 2025 Monisha Sood. Built with intention for Product Managers who care about craft.</p>
      </div>
    </div>
  </footer>

  <!-- Scroll to Top -->
  <a href="#home" class="scroll-top" id="scrollTop">↑</a>

  <script>
    // Scroll to top button
    const scrollTop = document.getElementById('scrollTop');
    
    window.addEventListener('scroll', () => {
      if (window.pageYOffset > 300) {
        scrollTop.classList.add('visible');
      } else {
        scrollTop.classList.remove('visible');
      }
    });
    
    // Typing animation for hero text
    const words = ['drive impact', 'solve problems', 'create value', 'scale systems'];
    let wordIndex = 0;
    let charIndex = 0;
    let isDeleting = false;
    const typingSpeed = 100;
    const deletingSpeed = 50;
    const pauseTime = 2000;
    
    function typeText() {
      const gradientText = document.querySelector('.gradient-text');
      if (!gradientText) return;
      
      const currentWord = words[wordIndex];
      
      if (isDeleting) {
        gradientText.textContent = currentWord.substring(0, charIndex - 1);
        charIndex--;
      } else {
        gradientText.textContent = currentWord.substring(0, charIndex + 1);
        charIndex++;
      }
      
      let timeout = isDeleting ? deletingSpeed : typingSpeed;
      
      if (!isDeleting && charIndex === currentWord.length) {
        timeout = pauseTime;
        isDeleting = true;
      } else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        wordIndex = (wordIndex + 1) % words.length;
      }
      
      setTimeout(typeText, timeout);
    }
    
    // Start typing animation after page load
    setTimeout(typeText, 1000);
    
    // Animate metrics on scroll
    const observerOptions = {
      threshold: 0.5,
      rootMargin: '0px'
    };
    
    const animateValue = (element, start, end, duration) => {
      const range = end - start;
      const increment = range / (duration / 16);
      let current = start;
      
      const timer = setInterval(() => {
        current += increment;
        if (current >= end) {
          element.textContent = formatNumber(end);
          clearInterval(timer);
        } else {
          element.textContent = formatNumber(Math.floor(current));
        }
      }, 16);
    };
    
    const formatNumber = (num) => {
      if (num >= 1000000) {
        return '$' + (num / 1000000).toFixed(0) + 'M+';
      } else if (num >= 1000) {
        return (num / 1000).toFixed(0) + 'K+';
      }
      return num + '+';
    };
    
    const metricObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting && !entry.target.classList.contains('animated')) {
          entry.target.classList.add('animated');
          const value = entry.target.querySelector('.metric-value');
          const text = value.textContent;
          
          if (text.includes('$')) {
            animateValue(value, 0, 50000000, 2000);
          } else if (text.includes('%')) {
            const num = parseInt(text);
            animateValue(value, 0, num, 1500);
            setTimeout(() => {
              value.textContent = num + '%';
            }, 1500);
          } else {
            const num = parseInt(text);
            let start = 0;
            const timer = setInterval(() => {
              start++;
              value.textContent = start + (text.includes('+') ? '+' : '');
              if (start >= num) clearInterval(timer);
            }, 100);
          }
        }
      });
    }, observerOptions);
    
    document.querySelectorAll('.metric-card').forEach(card => {
      metricObserver.observe(card);
    });
    
    // Animate sections on scroll
    const sectionObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.style.opacity = '1';
          entry.target.style.transform = 'translateY(0)';
        }
      });
    }, { threshold: 0.1 });
    
    document.querySelectorAll('.case-study, .principle-card, .skill-category, .award-card-modern').forEach(el => {
      el.style.opacity = '0';
      el.style.transform = 'translateY(30px)';
      el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
      sectionObserver.observe(el);
    });
    
    // Interactive skill items with progress bars
    document.querySelectorAll('.skill-item').forEach(item => {
      item.addEventListener('mouseenter', function() {
        this.style.transform = 'scale(1.05) translateY(-2px)';
      });
      
      item.addEventListener('mouseleave', function() {
        this.style.transform = 'scale(1) translateY(0)';
      });
    });
    
    // Add particle effect to hero
    function createParticle() {
      const hero = document.querySelector('.hero');
      const particle = document.createElement('div');
      particle.className = 'particle';
      particle.style.cssText = `
        position: absolute;
        width: 4px;
        height: 4px;
        background: var(--primary-light);
        border-radius: 50%;
        pointer-events: none;
        opacity: 0;
        animation: float-particle 4s ease-in-out forwards;
      `;
      
      particle.style.left = Math.random() * 100 + '%';
      particle.style.top = Math.random() * 100 + '%';
      
      hero.appendChild(particle);
      
      setTimeout(() => particle.remove(), 4000);
    }
    
    // Create particles periodically
    setInterval(createParticle, 800);
    
    // Add ripple effect on button clicks
    document.querySelectorAll('.btn, .profile-link').forEach(button => {
      button.addEventListener('click', function(e) {
        const ripple = document.createElement('span');
        const rect = this.getBoundingClientRect();
        const size = Math.max(rect.width, rect.height);
        const x = e.clientX - rect.left - size / 2;
        const y = e.clientY - rect.top - size / 2;
        
        ripple.style.cssText = `
          position: absolute;
          width: ${size}px;
          height: ${size}px;
          left: ${x}px;
          top: ${y}px;
          background: rgba(255, 255, 255, 0.5);
          border-radius: 50%;
          transform: scale(0);
          animation: ripple 0.6s ease-out;
          pointer-events: none;
        `;
        
        this.style.position = 'relative';
        this.style.overflow = 'hidden';
        this.appendChild(ripple);
        
        setTimeout(() => ripple.remove(), 600);
      });
    });
    
    // Smooth parallax effect for orbs
    let mouseX = 0;
    let mouseY = 0;
    
    document.addEventListener('mousemove', (e) => {
      mouseX = e.clientX / window.innerWidth;
      mouseY = e.clientY / window.innerHeight;
    });
    
    function animateOrbs() {
      const orb1 = document.querySelector('.orb1');
      const orb2 = document.querySelector('.orb2');
      
      if (orb1) {
        orb1.style.transform = `translate(${mouseX * 50}px, ${mouseY * 50}px)`;
      }
      if (orb2) {
        orb2.style.transform = `translate(${-mouseX * 30}px, ${-mouseY * 30}px)`;
      }
      
      requestAnimationFrame(animateOrbs);
    }
    
    animateOrbs();
    
    // Add tooltip for certifications
    document.querySelectorAll('a.skill-item').forEach(item => {
      const tooltip = document.createElement('div');
      tooltip.textContent = 'Click to verify';
      tooltip.style.cssText = `
        position: absolute;
        bottom: 100%;
        left: 50%;
        transform: translateX(-50%) translateY(-8px);
        background: var(--dark-surface);
        color: white;
        padding: 6px 12px;
        border-radius: 6px;
        font-size: 11px;
        white-space: nowrap;
        opacity: 0;
        pointer-events: none;
        transition: opacity 0.3s, transform 0.3s;
        border: 1px solid var(--border);
      `;
      
      item.style.position = 'relative';
      item.appendChild(tooltip);
      
      item.addEventListener('mouseenter', () => {
        tooltip.style.opacity = '1';
        tooltip.style.transform = 'translateX(-50%) translateY(-12px)';
      });
      
      item.addEventListener('mouseleave', () => {
        tooltip.style.opacity = '0';
        tooltip.style.transform = 'translateX(-50%) translateY(-8px)';
      });
    });
    
    // Add progress indicator to case studies
    const progressBar = document.createElement('div');
    progressBar.style.cssText = `
      position: fixed;
      top: 0;
      left: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--primary), var(--accent));
      width: 0%;
      z-index: 9999;
      transition: width 0.1s;
    `;
    document.body.appendChild(progressBar);
    
    window.addEventListener('scroll', () => {
      const scrollPercent = (window.scrollY / (document.documentElement.scrollHeight - window.innerHeight)) * 100;
      progressBar.style.width = scrollPercent + '%';
    });
  </script>
</body>
</html>
