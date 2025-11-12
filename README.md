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
    
    .orb3 {
      width: 300px;
      height: 300px;
      background: var(--accent);
      top: 50%;
      left: 50%;
      animation-delay: 10s;
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
      transition: all 0.3s;
    }
    
    nav.scrolled {
      padding: 12px 0;
      background: rgba(15, 23, 42, 0.95);
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
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
      cursor: pointer;
      transition: transform 0.3s;
    }
    
    .logo:hover {
      transform: scale(1.05);
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
    
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 2px;
      background: linear-gradient(90deg, var(--primary), var(--accent));
      transition: width 0.3s;
    }
    
    .nav-links a:hover::after,
    .nav-links a.active::after {
      width: 100%;
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
    
    /* Mobile Menu Toggle */
    .menu-toggle {
      display: none;
      flex-direction: column;
      gap: 6px;
      cursor: pointer;
      padding: 8px;
    }
    
    .menu-toggle span {
      width: 25px;
      height: 3px;
      background: var(--primary-light);
      border-radius: 2px;
      transition: all 0.3s;
    }
    
    .menu-toggle.active span:nth-child(1) {
      transform: rotate(45deg) translate(8px, 8px);
    }
    
    .menu-toggle.active span:nth-child(2) {
      opacity: 0;
    }
    
    .menu-toggle.active span:nth-child(3) {
      transform: rotate(-45deg) translate(8px, -8px);
    }
    
    /* Container */
    .container {
      max-width: 1400px;
      margin: 0 auto;
      padding: 0 40px;
      position: relative;
      z-index: 1;
    }
    
    /* Fade in on scroll animation */
    .fade-in {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.6s ease-out, transform 0.6s ease-out;
    }
    
    .fade-in.visible {
      opacity: 1;
      transform: translateY(0);
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
      display: inline-block;
      animation: gradientShift 3s ease infinite;
    }
    
    @keyframes gradientShift {
      0%, 100% { filter: hue-rotate(0deg); }
      50% { filter: hue-rotate(20deg); }
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
      position: relative;
      overflow: hidden;
    }
    
    .btn::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 0;
      height: 0;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.2);
      transform: translate(-50%, -50%);
      transition: width 0.6s, height 0.6s;
    }
    
    .btn:hover::before {
      width: 300px;
      height: 300px;
    }
    
    .btn span {
      position: relative;
      z-index: 1;
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
      cursor: pointer;
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
      cursor: pointer;
    }
    
    .profile-image-bg {
      position: absolute;
      inset: -8px;
      background: linear-gradient(135deg, var(--primary), var(--accent));
      border-radius: 50%;
      animation: rotate 8s linear infinite;
      opacity: 0.5;
    }
    
    .profile-image-container:hover .profile-image-bg {
      animation: rotate 4s linear infinite;
      opacity: 0.8;
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
      transition: transform 0.3s;
    }
    
    .profile-image-container:hover .profile-image {
      transform: scale(1.05);
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
    
    /* Product Case Studies */
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
      cursor: pointer;
    }
    
    .case-study::after {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, var(--primary) 0%, transparent 50%);
      opacity: 0;
      transition: opacity 0.4s;
      pointer-events: none;
    }
    
    .case-study:hover::after {
      opacity: 0.05;
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
      transition: all 0.3s;
    }
    
    .case-study:hover .company-tag {
      background: rgba(99, 102, 241, 0.25);
      transform: translateX(4px);
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
      transition: color 0.3s;
    }
    
    .case-study:hover h3 {
      color: var(--primary-light);
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
      transition: all 0.3s;
    }
    
    .case-study:hover .problem-statement {
      background: rgba(236, 72, 153, 0.12);
      transform: translateX(4px);
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
      transition: all 0.3s;
    }
    
    .solution-list li::before {
      content: '→';
      position: absolute;
      left: 0;
      color: var(--primary-light);
      font-weight: bold;
      transition: all 0.3s;
    }
    
    .solution-list li:hover {
      color: var(--primary-light);
      transform: translateX(4px);
    }
    
    .solution-list li:hover::before {
      transform: translateX(4px);
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
      transition: all 0.3s;
      cursor: pointer;
    }
    
    .impact-card:hover {
      background: rgba(16, 185, 129, 0.15);
      border-color: var(--success);
      transform: scale(1.05);
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
      transition: all 0.3s;
      cursor: pointer;
    }
    
    .tool-badge:hover {
      background: rgba(99, 102, 241, 0.15);
      border-color: var(--primary);
      color: var(--primary-light);
      transform: translateY(-2px);
    }
    
    /* PM Principles */
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
      cursor: pointer;
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
      transform: translateY(-8px) scale(1.02);
    }
    
    .principle-card:hover::before {
      opacity: 0.08;
    }
    
    .principle-icon {
      font-size: 40px;
      margin-bottom: 20px;
      position: relative;
      z-index: 1;
      display: inline-block;
      transition: transform 0.3s;
    }
    
    .principle-card:hover .principle-icon {
      transform: scale(1.2) rotate(10deg);
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
    
    /* Skills Section */
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
      transform: translateY(-4px);
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
    }
    
    .skill-item:hover {
      background: rgba(99, 102, 241, 0.2);
      border-color: var(--primary);
      transform: translateY(-2px);
      box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
    }
    
    /* Awards */
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
      cursor: pointer;
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
      transform: translateY(-8px) scale(1.05);
    }
    
    .award-card-modern:hover::before {
      opacity: 0.1;
    }
    
    .award-icon-modern {
      font-size: 48px;
      margin-bottom: 16px;
      position: relative;
      z-index: 1;
      display: inline-block;
      transition: transform 0.3s;
    }
    
    .award-card-modern:hover .award-icon-modern {
      transform: scale(1.3) rotate(15deg);
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
      transform: translateY(-4px) rotate(5deg);
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
      transition: all 0.3s;
    }
    
    .footer-section a:hover {
      color: var(--primary-light);
      transform: translateX(4px);
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
      transform: translateY(-8px) rotate(360deg);
      box-shadow: 0 12px 32px rgba(99, 102, 241, 0.5);
    }
    
    /* Cursor trail effect */
    .cursor-trail {
      position: fixed;
      width: 20px;
      height: 20px;
      border-radius: 50%;
      background: radial-gradient(circle, var(--primary-light), transparent);
      pointer-events: none;
      z-index: 9999;
      opacity: 0;
      transition: opacity 0.3s;
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
        grid-template-columns: repeat(2, 1fr);
      }
      
      .skills-categories {
        grid-template-columns: 1fr;
      }
      
      .awards-showcase {
        grid-template-columns: repeat(2, 1fr);
      }
      
      .footer-content {
        grid-template-columns: 1fr 1fr;
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
        position: fixed;
        top: 70px;
        left: 0;
        right: 0;
        background: rgba(15, 23, 42, 0.98);
        flex-direction: column;
        padding: 20px;
        gap: 20px;
        transform: translateY(-100%);
        opacity: 0;
        transition: all 0.3s;
        border-bottom: 1px solid var(--border);
      }
      
      .nav-links.active {
        transform: translateY(0);
        opacity: 1;
      }
      
      .menu-toggle {
        display: flex;
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
      
      .principles-grid {
        grid-template-columns: 1fr;
      }
      
      .awards-showcase {
        grid-template-columns: 1fr;
      }
      
      .footer-content {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <!-- Cursor trail elements -->
  <div class="cursor-trail" id="trail1"></div>
  <div class="cursor-trail" id="trail2"></div>
  <div class="cursor-trail" id="trail3"></div>

  <!-- Animated Background -->
  <div class="bg-animation">
    <div class="grid-bg"></div>
    <div class="orb orb1"></div>
    <div class="orb orb2"></div>
    <div class="orb orb3"></div>
  </div>

  <!-- Navigation -->
  <nav id="navbar">
    <div class="container">
      <div class="logo" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">MS</div>
      <div class="menu-toggle" id="menuToggle">
        <span></span>
        <span></span>
        <span></span>
      </div>
      <ul class="nav-links" id="navLinks">
        <li><a href="#home" class="nav-link">Home</a></li>
        <li><a href="#case-studies" class="nav-link">Case Studies</a></li>
        <li><a href="#principles" class="nav-link">Approach</a></li>
        <li><a href="#skills" class="nav-link">Skills</a></li>
        <li><a href="#awards" class="nav-link">Recognition</a></li>
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
              <span>View Case Studies →</span>
            </a>
            <a href="Monisha_Sood_Resume.pdf" class="btn btn-secondary" download>
              <span>Download Resume</span>
            </a>
            <a href="https://www.linkedin.com/in/monishasood07/" class="btn btn-secondary" target="_blank">
              <svg class="linkedin-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
              <span>LinkedIn</span>
            </a>
          </div>
        </div>
        
        <div class="hero-profile">
          <div class="profile-card">
            <div class="profile-image-container">
              <div class="profile-image-bg"></div>
              <img src="monisha-profile.png" alt="Monisha Sood" class="profile-image" onerror="this.src='https://ui-avatars.com/api/?name=Monisha+Sood&size=280&background=6366f1&color=fff&bold=true&font-size=0.4'">
            </div>
            <h3 class="profile-name">Monisha Sood</h3>
            <p class="profile-title">Product Manager | MBA '26</p>
            <div class="profile-links">
              <a href="Monisha_Sood_Resume.pdf" class="profile-link primary" download>
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
                  <polyline points="14 2 14 8 20 8"></polyline>
                  <line x1="16" y1="13" x2="8" y2="13"></line>
                  <line x1="16" y1="17" x2="8" y2="17"></line>
                  <polyline points="10 9 9 9 8 9"></polyline>
                </svg>
                Download Resume
              </a>
              <a href="https://www.linkedin.com/in/monishasood07/" class="profile-link" target="_blank">
                <svg class="linkedin-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                </svg>
                LinkedIn Profile
              </a>
              <a href="/cdn-cgi/l/email-protection#d8b5b7b6b1abb0b9f6abb7b7bc98afb1abbbf6bdbcad" class="profile-link">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                  <polyline points="22,6 12,13 2,6"></polyline>
                </svg>
                <span class="__cf_email__" data-cfemail="1d707273746e757c336e7272795d6a746e7e33787968">[email&#160;protected]</span>
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="hero-metrics">
        <div class="metric-card" data-count="6">
          <div class="metric-value">0+</div>
          <div class="metric-label">Years in Product</div>
          <div class="metric-change">↑ Growing</div>
        </div>
        <div class="metric-card" data-count="50">
          <div class="metric-value">$0M+</div>
          <div class="metric-label">Value Created</div>
          <div class="metric-change">↑ Contracts Closed</div>
        </div>
        <div class="metric-card" data-count="70">
          <div class="metric-value">0%</div>
          <div class="metric-label">Efficiency Gains</div>
          <div class="metric-change">↑ Through Automation</div>
        </div>
        <div class="metric-card" data-count="3">
          <div class="metric-value">0</div>
          <div class="metric-label">MVPs Launched</div>
          <div class="metric-change">↑ 0→1 Products</div>
        </div>
      </div>
    </div>
  </section>

  <!-- Product Case Studies Section -->
  <section id="case-studies">
    <div class="container">
      <div class="section-header fade-in">
        <span class="section-tag">PRODUCT WORK</span>
        <h2 class="section-title">Featured Case Studies</h2>
        <p class="section-description">
          Real product problems. Data-driven solutions. Measurable impact.
        </p>
      </div>
      
      <div class="case-studies">
        <!-- Case Study 1 -->
        <div class="case-study fade-in">
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

        <!-- Case Study 2 -->
        <div class="case-study fade-in">
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

        <!-- Case Study 3 -->
        <div class="case-study fade-in">
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
      <div class="section-header fade-in">
        <span class="section-tag">MY APPROACH</span>
        <h2 class="section-title">Product Philosophy</h2>
        <p class="section-description">
          How I think about building products that matter
        </p>
      </div>
      
      <div class="principles-grid">
        <div class="principle-card fade-in">
          <div class="principle-icon">
            <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--primary-light);">
              <circle cx="12" cy="12" r="10"></circle>
              <circle cx="12" cy="12" r="6"></circle>
              <circle cx="12" cy="12" r="2"></circle>
            </svg>
          </div>
          <h3>Start with the Problem</h3>
          <p>Great products emerge from deep customer understanding, not feature lists. I invest heavily in user research, qualitative feedback, and data analysis before writing a single user story.</p>
        </div>
        
        <div class="principle-card fade-in">
          <div class="principle-icon">
            <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--primary-light);">
              <line x1="18" y1="20" x2="18" y2="10"></line>
              <line x1="12" y1="20" x2="12" y2="4"></line>
              <line x1="6" y1="20" x2="6" y2="14"></line>
            </svg>
          </div>
          <h3>Let Data Drive Decisions</h3>
          <p>Opinions are cheap. Data is truth. I build dashboards, run A/B tests, and define clear metrics to validate assumptions and measure impact at every stage.</p>
        </div>
        
        <div class="principle-card fade-in">
          <div class="principle-icon">
            <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--primary-light);">
              <polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon>
            </svg>
          </div>
          <h3>Ship Fast, Learn Faster</h3>
          <p>MVPs beat perfection every time. I prioritize ruthlessly, cut scope aggressively, and iterate based on real user behavior rather than hypothetical requirements.</p>
        </div>
        
        <div class="principle-card fade-in">
          <div class="principle-icon">
            <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--primary-light);">
              <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path>
              <circle cx="9" cy="7" r="4"></circle>
              <path d="M23 21v-2a4 4 0 0 0-3-3.87"></path>
              <path d="M16 3.13a4 4 0 0 1 0 7.75"></path>
            </svg>
          </div>
          <h3>Cross-functional is Non-negotiable</h3>
          <p>Product managers are multipliers, not individual contributors. I build bridges between engineering, design, and business stakeholders to align everyone around shared goals.</p>
        </div>
        
        <div class="principle-card fade-in">
          <div class="principle-icon">
            <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--primary-light);">
              <circle cx="12" cy="12" r="3"></circle>
              <path d="M12 1v6m0 6v6m5.196-14.196l-4.243 4.243m0 5.656l-4.242 4.243m14.195-5.196l-6 0m-6 0l-6 0m14.196 5.196l-4.243-4.243m0-5.656l-4.242-4.243"></path>
            </svg>
          </div>
          <h3>Automate the Boring Stuff</h3>
          <p>Manual processes are technical debt. I build systems that scale, using tools like Zapier and Airtable to eliminate repetitive work and free teams to focus on what matters.</p>
        </div>
        
        <div class="principle-card fade-in">
          <div class="principle-icon">
            <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--primary-light);">
              <path d="M12 2v1m0 18v1M4.22 4.22l.71.71m14.14 14.14l.71.71M2 12h1m18 0h1M4.93 4.93l.71.71m12.73 12.73l.71.71M12 6a6 6 0 0 0 0 12c3.31 0 6-2.69 6-6a6 6 0 0 0-6-6z"></path>
              <path d="M9 21h6"></path>
            </svg>
          </div>
          <h3>Empathy + Execution</h3>
          <p>The best PMs balance vision with pragmatism. I care deeply about user problems while staying ruthlessly focused on delivering tangible business outcomes.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Skills Section -->
  <section id="skills">
    <div class="container">
      <div class="section-header fade-in">
        <span class="section-tag">CAPABILITIES</span>
        <h2 class="section-title">Product Management Toolkit</h2>
        <p class="section-description">
          Technical skills and methodologies I use to ship great products
        </p>
      </div>
      
      <div class="skills-categories">
        <div class="skill-category fade-in">
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
        
        <div class="skill-category fade-in">
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
        
        <div class="skill-category fade-in">
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
        
        <div class="skill-category fade-in">
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
      <div class="section-header fade-in">
        <span class="section-tag">RECOGNITION</span>
        <h2 class="section-title">Awards & Impact</h2>
        <p class="section-description">
          Recognized for driving measurable business outcomes
        </p>
      </div>
      
      <div class="awards-showcase">
        <div class="award-card-modern fade-in">
          <div class="award-icon-modern">
            <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--accent);">
              <path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"></path>
              <path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"></path>
              <path d="M4 22h16"></path>
              <path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"></path>
              <path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"></path>
              <path d="M18 2H6v7a6 6 0 0 0 12 0V2Z"></path>
            </svg>
          </div>
          <h3>Most Trusted Partner</h3>
          <p>Honored for closing $10M+ in contracts and building exceptional client relationships at Flyhomes</p>
        </div>
        
        <div class="award-card-modern fade-in">
          <div class="award-icon-modern">
            <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--accent);">
              <polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"></polygon>
            </svg>
          </div>
          <h3>Superstar of the Month</h3>
          <p>Awarded for 30% productivity improvement and exceeding targets through process innovation</p>
        </div>
        
        <div class="award-card-modern fade-in">
          <div class="award-icon-modern">
            <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color: var(--accent);">
              <path d="M4.5 16.5c-1.5 1.26-2 5-2 5s3.74-.5 5-2c.71-.84.7-2.13-.09-2.91a2.18 2.18 0 0 0-2.91-.09z"></path>
              <path d="m12 15-3-3a22 22 0 0 1 2-3.95A12.88 12.88 0 0 1 22 2c0 2.72-.78 7.5-6 11a22.35 22.35 0 0 1-4 2z"></path>
              <path d="M9 12H4s.55-3.03 2-4c1.62-1.08 5 0 5 0"></path>
              <path d="M12 15v5s3.03-.55 4-2c1.08-1.62 0-5 0-5"></path>
            </svg>
          </div>
          <h3>Product Impact Champion</h3>
          <p>Recognized for MVP launch that boosted engagement and reduced manual work by 70%</p>
        </div>
      </div>
      
      <div class="section-header fade-in" style="margin-top: 80px;">
        <span class="section-tag">CERTIFICATIONS</span>
        <h2 class="section-title">Continuous Learning</h2>
      </div>
      
      <div class="skills-categories">
        <div class="skill-category fade-in">
          <h3>Product & Business</h3>
          <div class="skill-items">
            <span class="skill-item">Product Management (Udemy)</span>
            <span class="skill-item">Business Management (London Business School)</span>
            <span class="skill-item">Generative AI for PM</span>
            <span class="skill-item">Six Sigma</span>
          </div>
        </div>
        
        <div class="skill-category fade-in">
          <h3>Technical & Analytics</h3>
          <div class="skill-items">
            <span class="skill-item">SQL Certification</span>
            <span class="skill-item">Power BI</span>
            <span class="skill-item">MS Excel Advanced</span>
            <span class="skill-item">Data Analysis</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Tools Used Section -->
  <section id="tools-used-section" style="padding: 80px 0;">
    <div class="container">
      <div class="section-header fade-in">
        <span class="section-tag">BUILT WITH</span>
        <h2 class="section-title">Tools & Technologies</h2>
        <p class="section-description">
          This portfolio was crafted using modern web technologies for optimal performance and interactivity
        </p>
      </div>
      
      <div class="skills-categories" style="grid-template-columns: repeat(3, 1fr);">
        <div class="skill-category fade-in">
          <h3>Frontend Technologies</h3>
          <div class="skill-items">
            <span class="skill-item">HTML5</span>
            <span class="skill-item">CSS3</span>
            <span class="skill-item">Vanilla JavaScript</span>
            <span class="skill-item">Responsive Design</span>
            <span class="skill-item">CSS Grid & Flexbox</span>
            <span class="skill-item">CSS Animations</span>
          </div>
        </div>
        
        <div class="skill-category fade-in">
          <h3>Design & UX</h3>
          <div class="skill-items">
            <span class="skill-item">Google Fonts</span>
            <span class="skill-item">Space Grotesk</span>
            <span class="skill-item">Inter</span>
            <span class="skill-item">Custom Color Palette</span>
            <span class="skill-item">Glassmorphism</span>
            <span class="skill-item">Gradient Design</span>
          </div>
        </div>
        
        <div class="skill-category fade-in">
          <h3>Interactive Features</h3>
          <div class="skill-items">
            <span class="skill-item">Intersection Observer API</span>
            <span class="skill-item">Scroll Animations</span>
            <span class="skill-item">Counter Animations</span>
            <span class="skill-item">Cursor Trail Effects</span>
            <span class="skill-item">Smooth Scrolling</span>
            <span class="skill-item">Hover Transitions</span>
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
            <a href="/cdn-cgi/l/email-protection#e78a88898e948f86c994888883a7908e9484c9828392" class="social-link" title="Email">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                <polyline points="22,6 12,13 2,6"></polyline>
              </svg>
            </a>
            <a href="Monisha_Sood_Resume.pdf" class="social-link" download title="Resume">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
                <polyline points="14 2 14 8 20 8"></polyline>
                <line x1="16" y1="13" x2="8" y2="13"></line>
                <line x1="16" y1="17" x2="8" y2="17"></line>
              </svg>
            </a>
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
            <li><a href="/cdn-cgi/l/email-protection#55383a3b3c263d347b263a3a3115223c26367b303120"><span class="__cf_email__" data-cfemail="f79a98999e849f96d984989893b7809e8494d9929382">[email&#160;protected]</span></a></li>
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

  <script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
    // Scroll animations
    const observerOptions = {
      threshold: 0.1,
      rootMargin: '0px 0px -100px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, observerOptions);

    document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

    // Scroll to top button
    const scrollTop = document.getElementById('scrollTop');
    
    window.addEventListener('scroll', () => {
      if (window.pageYOffset > 300) {
        scrollTop.classList.add('visible');
      } else {
        scrollTop.classList.remove('visible');
      }
      
      // Navbar scroll effect
      const navbar = document.getElementById('navbar');
      if (window.pageYOffset > 50) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    });

    // Mobile menu toggle
    const menuToggle = document.getElementById('menuToggle');
    const navLinks = document.getElementById('navLinks');
    
    menuToggle.addEventListener('click', () => {
      menuToggle.classList.toggle('active');
      navLinks.classList.toggle('active');
    });

    // Close mobile menu on link click
    document.querySelectorAll('.nav-link').forEach(link => {
      link.addEventListener('click', () => {
        menuToggle.classList.remove('active');
        navLinks.classList.remove('active');
      });
    });

    // Active nav link on scroll
    const sections = document.querySelectorAll('section');
    const navLinkElements = document.querySelectorAll('.nav-link');

    window.addEventListener('scroll', () => {
      let current = '';
      sections.forEach(section => {
        const sectionTop = section.offsetTop;
        const sectionHeight = section.clientHeight;
        if (pageYOffset >= sectionTop - 200) {
          current = section.getAttribute('id');
        }
      });

      navLinkElements.forEach(link => {
        link.classList.remove('active');
        if (link.getAttribute('href').slice(1) === current) {
          link.classList.add('active');
        }
      });
    });

    // Animate metric cards counter
    function animateValue(element, start, end, duration, suffix = '') {
      let startTimestamp = null;
      const step = (timestamp) => {
        if (!startTimestamp) startTimestamp = timestamp;
        const progress = Math.min((timestamp - startTimestamp) / duration, 1);
        const value = Math.floor(progress * (end - start) + start);
        
        if (suffix === 'M') {
          element.textContent = '$' + value + 'M+';
        } else if (suffix === '%') {
          element.textContent = value + '%';
        } else {
          element.textContent = value + '+';
        }
        
        if (progress < 1) {
          window.requestAnimationFrame(step);
        }
      };
      window.requestAnimationFrame(step);
    }

    // Trigger metric animations when in view
    const metricObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting && !entry.target.classList.contains('animated')) {
          entry.target.classList.add('animated');
          const valueElement = entry.target.querySelector('.metric-value');
          const targetValue = parseInt(entry.target.dataset.count);
          
          if (valueElement.textContent.includes('$')) {
            animateValue(valueElement, 0, targetValue, 2000, 'M');
          } else if (valueElement.textContent.includes('%')) {
            animateValue(valueElement, 0, targetValue, 2000, '%');
          } else {
            animateValue(valueElement, 0, targetValue, 2000);
          }
        }
      });
    }, { threshold: 0.5 });

    document.querySelectorAll('.metric-card').forEach(card => {
      metricObserver.observe(card);
    });

    // Cursor trail effect
    const trails = [
      document.getElementById('trail1'),
      document.getElementById('trail2'),
      document.getElementById('trail3')
    ];
    
    let mouseX = 0, mouseY = 0;
    let trail1X = 0, trail1Y = 0;
    let trail2X = 0, trail2Y = 0;
    let trail3X = 0, trail3Y = 0;

    document.addEventListener('mousemove', (e) => {
      mouseX = e.clientX;
      mouseY = e.clientY;
    });

    function animateTrails() {
      // Smooth following with different speeds
      trail1X += (mouseX - trail1X) * 0.3;
      trail1Y += (mouseY - trail1Y) * 0.3;
      
      trail2X += (mouseX - trail2X) * 0.15;
      trail2Y += (mouseY - trail2Y) * 0.15;
      
      trail3X += (mouseX - trail3X) * 0.08;
      trail3Y += (mouseY - trail3Y) * 0.08;

      trails[0].style.left = trail1X + 'px';
      trails[0].style.top = trail1Y + 'px';
      trails[0].style.opacity = '0.6';
      
      trails[1].style.left = trail2X + 'px';
      trails[1].style.top = trail2Y + 'px';
      trails[1].style.opacity = '0.4';
      
      trails[2].style.left = trail3X + 'px';
      trails[2].style.top = trail3Y + 'px';
      trails[2].style.opacity = '0.2';

      requestAnimationFrame(animateTrails);
    }

    animateTrails();

    // Smooth scrol
