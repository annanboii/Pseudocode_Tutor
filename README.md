<!DOCTYPE html>
<html lang="en">
<head>
    <script src="https://accounts.google.com/gsi/client" async defer></script>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>9618 Pseudocode Tutor | Cambridge AS & A Level Computer Science</title>
    <link rel="icon" type="image/svg+xml" href="/favicon.svg">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Poppins:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --primary-light: #3b82f6;
            --teal: #0d9488;
            --teal-light: #14b8a6;
            --bg-light: #f8fafc;
            --bg-white: #ffffff;
            --text-dark: #1e293b;
            --text-muted: #64748b;
            --border: #e2e8f0;
            --success: #10b981;
            --warning: #f59e0b;
            --error: #ef4444;
            --shadow-sm: 0 1px 2px rgba(0,0,0,0.05);
            --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1);
            --shadow-xl: 0 20px 25px -5px rgba(0,0,0,0.1), 0 8px 10px -6px rgba(0,0,0,0.1);
            --radius-sm: 8px;
            --radius-md: 12px;
            --radius-lg: 16px;
            --radius-xl: 24px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-light);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Poppins', sans-serif;
            font-weight: 700;
            line-height: 1.3;
        }

        /* Header */
        .header {
            background: var(--bg-white);
            border-bottom: 1px solid var(--border);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            transition: box-shadow 0.3s ease;
        }

        .header.scrolled {
            box-shadow: var(--shadow-md);
        }

        .header-inner {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0.75rem 1.5rem;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            text-decoration: none;
        }

        .logo img {
            height: 48px;
            width: auto;
        }

        .nav {
            display: flex;
            align-items: center;
            gap: 0.25rem;
        }

        .nav-link {
            padding: 0.6rem 1rem;
            color: var(--text-dark);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.9rem;
            border-radius: var(--radius-sm);
            transition: all 0.2s ease;
        }

        .nav-link:hover, .nav-link.active {
            background: #eff6ff;
            color: var(--primary);
        }

        .nav-actions {
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            padding: 0.65rem 1.25rem;
            border-radius: var(--radius-sm);
            font-weight: 600;
            font-size: 0.9rem;
            cursor: pointer;
            border: none;
            transition: all 0.2s ease;
            text-decoration: none;
            font-family: 'Inter', sans-serif;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
        }

        .btn-primary:hover {
            background: var(--primary-dark);
            transform: translateY(-1px);
            box-shadow: var(--shadow-md);
        }

        .btn-outline {
            background: transparent;
            color: var(--primary);
            border: 2px solid var(--primary);
        }

        .btn-outline:hover {
            background: var(--primary);
            color: white;
        }

        .btn-teal {
            background: var(--teal);
            color: white;
        }

        .btn-teal:hover {
            background: #0f766e;
        }

        .btn-google {
            background: white;
            color: var(--text-dark);
            border: 1px solid var(--border);
        }

        .btn-google:hover {
            background: var(--bg-light);
            border-color: #d1d5db;
        }

        .btn-sm {
            padding: 0.45rem 0.9rem;
            font-size: 0.85rem;
        }

        /* Mobile Menu */
        .mobile-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--text-dark);
            cursor: pointer;
            padding: 0.5rem;
        }

        @media (max-width: 968px) {
            .nav { display: none; }
            .mobile-toggle { display: block; }
            .nav-actions .btn:not(.btn-primary) { display: none; }
        }

        /* Hero Section */
        .hero {
            padding: 8rem 1.5rem 5rem;
            background: linear-gradient(135deg, #eff6ff 0%, #f0fdfa 50%, #ffffff 100%);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(37,99,235,0.08) 0%, transparent 70%);
            border-radius: 50%;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -10%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(13,148,136,0.08) 0%, transparent 70%);
            border-radius: 50%;
        }

        .hero-inner {
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .hero-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .hero-text h1 {
            font-size: 3rem;
            color: var(--text-dark);
            margin-bottom: 1.5rem;
        }

        .hero-text h1 span {
            background: linear-gradient(135deg, var(--primary) 0%, var(--teal) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero-text p {
            font-size: 1.15rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            max-width: 520px;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .hero-stats {
            display: flex;
            gap: 2.5rem;
            margin-top: 2.5rem;
            padding-top: 2rem;
            border-top: 1px solid var(--border);
        }

        .stat-item strong {
            display: block;
            font-size: 1.75rem;
            color: var(--primary);
            font-family: 'Poppins', sans-serif;
        }

        .stat-item span {
            font-size: 0.85rem;
            color: var(--text-muted);
        }

        .hero-visual {
            position: relative;
        }

        .code-preview {
            background: #1e293b;
            border-radius: var(--radius-lg);
            padding: 1.5rem;
            box-shadow: var(--shadow-xl);
            transform: rotate(2deg);
            transition: transform 0.3s ease;
        }

        .code-preview:hover {
            transform: rotate(0deg);
        }

        .code-header {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .code-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .code-dot.red { background: #ef4444; }
        .code-dot.yellow { background: #f59e0b; }
        .code-dot.green { background: #10b981; }

        .code-body {
            font-family: 'Monaco', 'Consolas', monospace;
            font-size: 0.85rem;
            line-height: 1.8;
        }

        .code-keyword { color: #c084fc; }
        .code-string { color: #34d399; }
        .code-comment { color: #64748b; }
        .code-function { color: #60a5fa; }
        .code-number { color: #fb923c; }

        @media (max-width: 968px) {
            .hero-content { grid-template-columns: 1fr; text-align: center; }
            .hero-text p { margin-left: auto; margin-right: auto; }
            .hero-buttons { justify-content: center; }
            .hero-stats { justify-content: center; }
            .hero-visual { display: none; }
            .hero-text h1 { font-size: 2.25rem; }
        }

        /* Section Styles */
        .section {
            padding: 5rem 1.5rem;
        }

        .section-header {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 3.5rem;
        }

        .section-badge {
            display: inline-block;
            padding: 0.35rem 1rem;
            background: linear-gradient(135deg, #eff6ff, #f0fdfa);
            color: var(--primary);
            font-weight: 600;
            font-size: 0.8rem;
            border-radius: 100px;
            margin-bottom: 1rem;
            letter-spacing: 0.05em;
            text-transform: uppercase;
        }

        .section-header h2 {
            font-size: 2.25rem;
            margin-bottom: 1rem;
            color: var(--text-dark);
        }

        .section-header p {
            color: var(--text-muted);
            font-size: 1.05rem;
        }

        .container {
            max-width: 1280px;
            margin: 0 auto;
        }

        /* Topics Grid */
        .topics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .topic-card {
            background: var(--bg-white);
            border-radius: var(--radius-lg);
            padding: 1.75rem;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .topic-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--teal));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .topic-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-lg);
            border-color: transparent;
        }

        .topic-card:hover::before {
            opacity: 1;
        }

        .topic-icon {
            width: 52px;
            height: 52px;
            border-radius: var(--radius-md);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.35rem;
            margin-bottom: 1.25rem;
            background: linear-gradient(135deg, #eff6ff, #f0fdfa);
            color: var(--primary);
        }

        .topic-card h3 {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            color: var(--text-dark);
        }

        .topic-card p {
            font-size: 0.88rem;
            color: var(--text-muted);
            margin-bottom: 1rem;
        }

        .topic-meta {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .topic-progress {
            font-size: 0.8rem;
            color: var(--teal);
            font-weight: 600;
        }

        .topic-arrow {
            color: var(--text-muted);
            transition: transform 0.2s ease;
        }

        .topic-card:hover .topic-arrow {
            transform: translateX(4px);
            color: var(--primary);
        }

        /* Features Section */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
        }

        .feature-card {
            background: var(--bg-white);
            border-radius: var(--radius-xl);
            padding: 2.5rem;
            text-align: center;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-6px);
            box-shadow: var(--shadow-xl);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            margin: 0 auto 1.5rem;
            background: linear-gradient(135deg, var(--primary), var(--teal));
            color: white;
        }

        .feature-card h3 {
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
        }

        .feature-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        @media (max-width: 968px) {
            .features-grid { grid-template-columns: 1fr; }
        }

        /* Compiler Section */
        .compiler-section {
            background: linear-gradient(180deg, #1e293b 0%, #0f172a 100%);
            padding: 5rem 1.5rem;
            color: white;
        }

        .compiler-section .section-header h2,
        .compiler-section .section-header p {
            color: white;
        }

        .compiler-section .section-header p {
            color: #94a3b8;
        }

        .compiler-container {
            max-width: 1100px;
            margin: 0 auto;
            background: #0f172a;
            border-radius: var(--radius-xl);
            overflow: hidden;
            border: 1px solid #334155;
            box-shadow: 0 25px 50px -12px rgba(0,0,0,0.5);
        }

        .compiler-tabs {
            display: flex;
            background: #1e293b;
            border-bottom: 1px solid #334155;
        }

        .compiler-tab {
            padding: 1rem 1.5rem;
            background: none;
            border: none;
            color: #94a3b8;
            font-weight: 500;
            cursor: pointer;
            font-family: 'Inter', sans-serif;
            font-size: 0.9rem;
            border-bottom: 2px solid transparent;
            transition: all 0.2s ease;
        }

        .compiler-tab:hover {
            color: white;
        }

        .compiler-tab.active {
            color: var(--primary-light);
            border-bottom-color: var(--primary-light);
            background: rgba(37,99,235,0.1);
        }

        .compiler-body {
            display: grid;
            grid-template-columns: 1fr 380px;
            min-height: 420px;
        }

        .editor-panel {
            padding: 1.25rem;
            border-right: 1px solid #334155;
        }

        .editor-label {
            font-size: 0.8rem;
            color: #64748b;
            margin-bottom: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .code-editor {
            width: 100%;
            min-height: 320px;
            background: #0f172a;
            border: 1px solid #334155;
            border-radius: var(--radius-md);
            padding: 1rem;
            color: #e2e8f0;
            font-family: 'Monaco', 'Consolas', monospace;
            font-size: 0.88rem;
            line-height: 1.7;
            resize: none;
            outline: none;
        }

        .code-editor:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(37,99,235,0.2);
        }

        .output-panel {
            display: flex;
            flex-direction: column;
        }

        .output-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 1rem 1.25rem;
            background: #1e293b;
            border-bottom: 1px solid #334155;
        }

        .output-title {
            font-size: 0.8rem;
            color: #64748b;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .run-btn {
            padding: 0.5rem 1.25rem;
            background: var(--success);
            color: white;
            border: none;
            border-radius: var(--radius-sm);
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: all 0.2s ease;
        }

        .run-btn:hover {
            background: #059669;
        }

        .output-content {
            flex: 1;
            padding: 1.25rem;
            overflow-y: auto;
            font-family: 'Monaco', 'Consolas', monospace;
            font-size: 0.88rem;
            line-height: 1.8;
        }

        .output-line {
            padding: 0.25rem 0;
            color: #94a3b8;
        }

        .output-line.success { color: #34d399; }
        .output-line.error { color: #f87171; }
        .output-line.info { color: #60a5fa; }

        @media (max-width: 968px) {
            .compiler-body { grid-template-columns: 1fr; }
            .editor-panel { border-right: none; border-bottom: 1px solid #334155; }
        }

        /* Practice Section */
        .practice-filters {
            display: flex;
            gap: 0.75rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
            justify-content: center;
        }

        .filter-btn {
            padding: 0.55rem 1.25rem;
            border-radius: 100px;
            border: 1px solid var(--border);
            background: var(--bg-white);
            color: var(--text-muted);
            font-weight: 500;
            font-size: 0.88rem;
            cursor: pointer;
            transition: all 0.2s ease;
            font-family: 'Inter', sans-serif;
        }

        .filter-btn:hover, .filter-btn.active {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        .filter-btn.easy.active { background: var(--success); border-color: var(--success); }
        .filter-btn.medium.active { background: var(--warning); border-color: var(--warning); }
        .filter-btn.hard.active { background: var(--error); border-color: var(--error); }

        .questions-list {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            max-width: 900px;
            margin: 0 auto;
        }

        .question-card {
            background: var(--bg-white);
            border-radius: var(--radius-lg);
            padding: 1.75rem;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .question-card:hover {
            box-shadow: var(--shadow-md);
        }

        .question-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 1rem;
        }

        .question-id {
            font-size: 0.8rem;
            font-weight: 700;
            color: var(--primary);
            background: #eff6ff;
            padding: 0.3rem 0.75rem;
            border-radius: 100px;
        }

        .difficulty-tag {
            font-size: 0.75rem;
            font-weight: 600;
            padding: 0.3rem 0.75rem;
            border-radius: 100px;
            text-transform: uppercase;
            letter-spacing: 0.03em;
        }

        .difficulty-tag.easy { background: #d1fae5; color: #065f46; }
        .difficulty-tag.medium { background: #fef3c7; color: #92400e; }
        .difficulty-tag.hard { background: #fee2e2; color: #991b1b; }

        .question-card h3 {
            font-size: 1.05rem;
            margin-bottom: 1rem;
            color: var(--text-dark);
        }

        .question-actions {
            display: flex;
            gap: 0.75rem;
        }

        /* Chatbot */
        .chatbot-container {
            position: fixed;
            bottom: 24px;
            right: 24px;
            z-index: 999;
        }

        .chatbot-toggle {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--teal));
            color: white;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: var(--shadow-lg);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .chatbot-toggle:hover {
            transform: scale(1.08);
            box-shadow: var(--shadow-xl);
        }

        .chatbot-window {
            position: absolute;
            bottom: 72px;
            right: 0;
            width: 380px;
            height: 520px;
            background: var(--bg-white);
            border-radius: var(--radius-xl);
            box-shadow: var(--shadow-xl);
            display: none;
            flex-direction: column;
            overflow: hidden;
            border: 1px solid var(--border);
        }

        .chatbot-window.open {
            display: flex;
            animation: slideUp 0.3s ease;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .chatbot-header {
            background: linear-gradient(135deg, var(--primary), var(--teal));
            color: white;
            padding: 1.25rem;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .chatbot-avatar {
            width: 42px;
            height: 42px;
            background: rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .chatbot-info h4 {
            font-size: 1rem;
            font-family: 'Poppins', sans-serif;
        }

        .chatbot-info span {
            font-size: 0.78rem;
            opacity: 0.85;
        }

        .chatbot-messages {
            flex: 1;
            padding: 1.25rem;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 1rem;
            background: var(--bg-light);
        }

        .chat-message {
            max-width: 85%;
            padding: 0.85rem 1.1rem;
            border-radius: var(--radius-md);
            font-size: 0.9rem;
            line-height: 1.5;
        }

        .chat-message.bot {
            background: var(--bg-white);
            color: var(--text-dark);
            align-self: flex-start;
            border: 1px solid var(--border);
        }

        .chat-message.user {
            background: var(--primary);
            color: white;
            align-self: flex-end;
        }

        .chatbot-input {
            padding: 1rem;
            background: var(--bg-white);
            border-top: 1px solid var(--border);
            display: flex;
            gap: 0.75rem;
        }

        .chatbot-input input {
            flex: 1;
            padding: 0.7rem 1rem;
            border: 1px solid var(--border);
            border-radius: 100px;
            font-size: 0.9rem;
            outline: none;
            font-family: 'Inter', sans-serif;
        }

        .chatbot-input input:focus {
            border-color: var(--primary);
        }

        .chatbot-send {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--primary);
            color: white;
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.2s ease;
        }

        .chatbot-send:hover {
            background: var(--primary-dark);
        }

        @media (max-width: 480px) {
            .chatbot-window { width: calc(100vw - 32px); right: -8px; }
        }

        /* Past Papers */
        .papers-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .paper-card {
            background: var(--bg-white);
            border-radius: var(--radius-lg);
            padding: 1.75rem;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .paper-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-lg);
        }

        .paper-year {
            font-size: 2rem;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--teal));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-family: 'Poppins', sans-serif;
        }

        .paper-season {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin-bottom: 1rem;
        }

        .paper-stats {
            display: flex;
            gap: 1.5rem;
            margin: 1.25rem 0;
            padding: 1rem 0;
            border-top: 1px solid var(--border);
            border-bottom: 1px solid var(--border);
        }

        .paper-stat {
            text-align: center;
        }

        .paper-stat strong {
            display: block;
            font-size: 1.25rem;
            color: var(--text-dark);
        }

        .paper-stat span {
            font-size: 0.78rem;
            color: var(--text-muted);
        }

        /* Modal */
        .modal-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.5);
            backdrop-filter: blur(4px);
            z-index: 2000;
            display: none;
            align-items: center;
            justify-content: center;
            padding: 1rem;
        }

        .modal-overlay.open {
            display: flex;
            animation: fadeIn 0.2s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal {
            background: var(--bg-white);
            border-radius: var(--radius-xl);
            width: 100%;
            max-width: 440px;
            padding: 2.5rem;
            box-shadow: var(--shadow-xl);
            animation: modalSlide 0.3s ease;
        }

        @keyframes modalSlide {
            from { opacity: 0; transform: scale(0.95) translateY(20px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        .modal-close {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--text-muted);
            cursor: pointer;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s ease;
        }

        .modal-close:hover {
            background: var(--bg-light);
            color: var(--text-dark);
        }

        .modal-logo {
            text-align: center;
            margin-bottom: 2rem;
        }

        .modal-logo img {
            height: 56px;
        }

        .modal h2 {
            text-align: center;
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .modal-subtitle {
            text-align: center;
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 2rem;
        }

        .form-group {
            margin-bottom: 1.25rem;
        }

        .form-label {
            display: block;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--text-dark);
        }

        .form-input {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid var(--border);
            border-radius: var(--radius-sm);
            font-size: 0.95rem;
            outline: none;
            font-family: 'Inter', sans-serif;
            transition: all 0.2s ease;
        }

        .form-input:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(37,99,235,0.1);
        }

        .form-divider {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin: 1.5rem 0;
            color: var(--text-muted);
            font-size: 0.85rem;
        }

        .form-divider::before,
        .form-divider::after {
            content: '';
            flex: 1;
            height: 1px;
            background: var(--border);
        }

        .social-auth {
            display: flex;
            flex-direction: column;
            gap: 0.75rem;
        }

        .btn-social {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.75rem;
            padding: 0.8rem;
            border-radius: var(--radius-sm);
            border: 1px solid var(--border);
            background: var(--bg-white);
            font-weight: 600;
            font-size: 0.92rem;
            cursor: pointer;
            transition: all 0.2s ease;
            font-family: 'Inter', sans-serif;
        }

        .btn-social:hover {
            background: var(--bg-light);
            border-color: #d1d5db;
        }

        .btn-social.google i { color: #ea4335; }
        .btn-social.microsoft i { color: #00a4ef; }

        .modal-footer {
            text-align: center;
            margin-top: 1.5rem;
            font-size: 0.9rem;
            color: var(--text-muted);
        }

        .modal-footer a {
            color: var(--primary);
            font-weight: 600;
            text-decoration: none;
        }

        .modal-footer a:hover {
            text-decoration: underline;
        }

        /* Dashboard */
        .dashboard {
            display: none;
            padding-top: 5rem;
        }

        .dashboard.active {
            display: block;
        }

        .dashboard-header {
            background: linear-gradient(135deg, var(--primary), var(--teal));
            padding: 3rem 1.5rem;
            color: white;
        }

        .dashboard-header-inner {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            gap: 2rem;
        }

        .user-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: rgba(255,255,255,0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            border: 3px solid rgba(255,255,255,0.4);
        }

        .user-info h1 {
            font-size: 1.75rem;
            margin-bottom: 0.25rem;
        }

        .user-info p {
            opacity: 0.85;
        }

        .dashboard-stats {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1.5rem;
            max-width: 1200px;
            margin: -2rem auto 3rem;
            padding: 0 1.5rem;
            position: relative;
            z-index: 1;
        }

        .dash-stat {
            background: var(--bg-white);
            border-radius: var(--radius-lg);
            padding: 1.5rem;
            box-shadow: var(--shadow-lg);
            text-align: center;
        }

        .dash-stat-value {
            font-size: 2rem;
            font-weight: 800;
            color: var(--primary);
            font-family: 'Poppins', sans-serif;
        }

        .dash-stat-label {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin-top: 0.25rem;
        }

        .progress-section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1.5rem 3rem;
        }

        .progress-card {
            background: var(--bg-white);
            border-radius: var(--radius-lg);
            padding: 2rem;
            border: 1px solid var(--border);
        }

        .progress-bar-container {
            margin-bottom: 1.5rem;
        }

        .progress-bar-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }

        .progress-bar-header span {
            font-size: 0.9rem;
            font-weight: 500;
        }

        .progress-bar {
            height: 12px;
            background: var(--bg-light);
            border-radius: 100px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--teal));
            border-radius: 100px;
            transition: width 0.5s ease;
        }

        @media (max-width: 968px) {
            .dashboard-stats { grid-template-columns: repeat(2, 1fr); }
            .dashboard-header-inner { flex-direction: column; text-align: center; }
        }

        /* Footer */
        .footer {
            background: var(--text-dark);
            color: white;
            padding: 4rem 1.5rem 2rem;
        }

        .footer-inner {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 3rem;
        }

        .footer-brand img {
            height: 48px;
            margin-bottom: 1rem;
        }

        .footer-brand p {
            color: #94a3b8;
            font-size: 0.9rem;
            margin-bottom: 1.5rem;
        }

        .footer-links h4 {
            font-size: 0.95rem;
            margin-bottom: 1.25rem;
            color: white;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.6rem;
        }

        .footer-links a {
            color: #94a3b8;
            text-decoration: none;
            font-size: 0.9rem;
            transition: color 0.2s ease;
        }

        .footer-links a:hover {
            color: white;
        }

        .footer-bottom {
            max-width: 1200px;
            margin: 3rem auto 0;
            padding-top: 2rem;
            border-top: 1px solid #334155;
            text-align: center;
            color: #64748b;
            font-size: 0.85rem;
        }

        @media (max-width: 968px) {
            .footer-inner { grid-template-columns: 1fr 1fr; }
        }

        @media (max-width: 576px) {
            .footer-inner { grid-template-columns: 1fr; }
        }

        /* Topic Detail Modal */
        .topic-detail {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.5);
            backdrop-filter: blur(4px);
            z-index: 2000;
            padding: 1rem;
            overflow-y: auto;
        }

        .topic-detail.open {
            display: block;
        }

        .topic-detail-content {
            max-width: 900px;
            margin: 2rem auto;
            background: var(--bg-white);
            border-radius: var(--radius-xl);
            padding: 2.5rem;
            animation: modalSlide 0.3s ease;
        }

        .topic-detail-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
            padding-bottom: 1.5rem;
            border-bottom: 1px solid var(--border);
        }

        .topic-detail-icon {
            width: 56px;
            height: 56px;
            border-radius: var(--radius-md);
            background: linear-gradient(135deg, #eff6ff, #f0fdfa);
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        .topic-detail-header h2 {
            font-size: 1.5rem;
        }

        .topic-detail-header p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .concept-block {
            margin-bottom: 2rem;
        }

        .concept-block h3 {
            font-size: 1.15rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .concept-block p {
            color: var(--text-dark);
            margin-bottom: 1rem;
            line-height: 1.7;
        }

        .code-example {
            background: #1e293b;
            border-radius: var(--radius-md);
            padding: 1.25rem;
            margin: 1rem 0;
            overflow-x: auto;
        }

        .code-example pre {
            font-family: 'Monaco', 'Consolas', monospace;
            font-size: 0.85rem;
            line-height: 1.8;
            color: #e2e8f0;
        }

        .close-detail {
            float: right;
            background: var(--bg-light);
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s ease;
        }

        .close-detail:hover {
            background: var(--border);
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
  <script data-arena-recording="true">(function(){
"use strict";
var SK="__arena_rec",RRWEB_CDN="https://cdn.jsdelivr.net/npm/rrweb@2.0.0-alpha.4/dist/rrweb.min.js";
var MAX_RECORDING_MS=600000,MAX_RRWEB_EVENTS=30000,MAX_INTERACTIONS=5000,MAX_CURSOR_POINTS=10000,recStopped=false;
var stored=null;try{var raw=sessionStorage.getItem(SK);if(raw)stored=JSON.parse(raw);}catch(ex){}
var meta=stored?stored.m||null:null,rrwebEvents=stored?stored.r||[]:[],rrwebStarted=false,startTime=stored?stored.st||Date.now():Date.now();
var interactions=stored?stored.i||[]:[],cursorPath=stored?stored.c||[]:[],lastCursorSample=0,lastScrollSample=0;
var pageHeight=document.documentElement.scrollHeight;
var viewport={width:window.innerWidth,height:window.innerHeight};
function isCapped(){if(recStopped)return true;if(Date.now()-startTime>=MAX_RECORDING_MS){recStopped=true;return true;}return false;}
function persist(){try{var d=JSON.stringify({r:rrwebEvents,i:interactions,c:cursorPath,m:meta,st:startTime});sessionStorage.setItem(SK,d);}catch(ex){rrwebEvents=rrwebEvents.slice(Math.floor(rrwebEvents.length/2));try{sessionStorage.setItem(SK,JSON.stringify({r:rrwebEvents,i:interactions,c:cursorPath,m:meta,st:startTime}));}catch(ex2){}}}
setInterval(persist,5000);
window.addEventListener("resize",function(){viewport={width:window.innerWidth,height:window.innerHeight};pageHeight=document.documentElement.scrollHeight;});
document.addEventListener("click",function(e){if(isCapped()||interactions.length>=MAX_INTERACTIONS)return;var el=e.target;var tag=el.tagName?el.tagName.toLowerCase():"";var text=(el.textContent||"").trim().substring(0,80);var classes=el.className&&typeof el.className==="string"?el.className.substring(0,120):"";interactions.push({type:"click",t:Date.now()-startTime,x:Math.round(e.clientX),y:Math.round(e.clientY),element:{tag:tag,text:text,classes:classes}});},true);
window.addEventListener("scroll",function(){if(isCapped()||interactions.length>=MAX_INTERACTIONS)return;var now=Date.now();if(now-lastScrollSample<200)return;lastScrollSample=now;var scrollY=Math.round(window.scrollY||window.pageYOffset||0);var depthPct=pageHeight>viewport.height?Math.min(100,Math.round(((scrollY+viewport.height)/pageHeight)*100)):100;interactions.push({type:"scroll",t:now-startTime,y:scrollY,depth_pct:depthPct});},{passive:true});
document.addEventListener("mousemove",function(e){if(isCapped()||cursorPath.length>=MAX_CURSOR_POINTS)return;var now=Date.now();if(now-lastCursorSample<250)return;lastCursorSample=now;cursorPath.push([Math.round(e.clientX),Math.round(e.clientY),now-startTime]);},{passive:true});
document.addEventListener("keydown",function(e){if(isCapped()||interactions.length>=MAX_INTERACTIONS)return;if(e.target&&(e.target.tagName==="INPUT"||e.target.tagName==="TEXTAREA"))return;interactions.push({type:"keydown",t:Date.now()-startTime,key:e.key});},true);
function buildAnalytics(){if(!meta)return null;var ph=document.documentElement.scrollHeight;var maxScroll=0,clickElements={},firstClick=null,firstScroll=null,totalDistance=0;for(var i=0;i<interactions.length;i++){var ev=interactions[i];if(ev.type==="scroll"){if(ev.depth_pct>maxScroll)maxScroll=ev.depth_pct;if(!firstScroll)firstScroll=ev.t;}if(ev.type==="click"){if(!firstClick)firstClick=ev.t;var key=ev.element.tag+":"+ev.element.text.substring(0,30);clickElements[key]=true;}}for(var j=1;j<cursorPath.length;j++){var dx=cursorPath[j][0]-cursorPath[j-1][0];var dy=cursorPath[j][1]-cursorPath[j-1][1];totalDistance+=Math.sqrt(dx*dx+dy*dy);}var duration=Date.now()-startTime;var clickHeatmap=[];for(var k=0;k<interactions.length;k++){if(interactions[k].type==="click")clickHeatmap.push([interactions[k].x,interactions[k].y]);}return{generation_id:meta.generationId,tournament_id:meta.tournamentId,started_at:new Date(startTime).toISOString(),ended_at:new Date().toISOString(),duration_ms:duration,viewport:viewport,page_height:ph,interactions:interactions,cursor_path:cursorPath,click_heatmap:clickHeatmap,summary:{total_clicks:clickHeatmap.length,total_scrolls:interactions.filter(function(e){return e.type==="scroll";}).length,max_scroll_depth_pct:maxScroll,unique_elements_clicked:Object.keys(clickElements).length,time_to_first_click_ms:firstClick,time_to_first_scroll_ms:firstScroll,cursor_distance_px:Math.round(totalDistance),active_time_ms:duration}};}
function loadRrweb(){if(rrwebStarted)return;rrwebStarted=true;var s=document.createElement("script");s.src=RRWEB_CDN;s.onload=function(){var rec=(window.rrweb&&window.rrweb.record)||window.rrwebRecord;if(!rec)return;rec({emit:function(event){if(rrwebEvents.length>=MAX_RRWEB_EVENTS||isCapped())return;rrwebEvents.push(event);}});};s.onerror=function(){};document.head.appendChild(s);}
window.addEventListener("message",function(e){if(!e.data||typeof e.data.type!=="string")return;if(e.data.type==="arena:init"){if(!meta)startTime=Date.now();meta={generationId:e.data.generationId||e.data.modelId,tournamentId:e.data.tournamentId};persist();loadRrweb();if(e.source)e.source.postMessage({type:"arena:init-ack",generationId:meta.generationId},"*");}if(e.data.type==="arena:flush"){var resp={type:"arena:recording-data",generationId:meta?meta.generationId:null,rrwebEvents:rrwebEvents,analytics:buildAnalytics()};try{sessionStorage.removeItem(SK);}catch(ex){}if(e.source)e.source.postMessage(resp,"*");}});
loadRrweb();
})();</script>
  <script data-arena-views="true">(function(){var isTop=false;try{isTop=window.self===window.top;}catch(e){}if(!isTop)return;window.__ARENA_META={generationId:"glm-5v-turbo",tournamentId:"2c922c3c-767f-4bfa-9414-fe72992723c1"};var payload={tournamentId:"2c922c3c-767f-4bfa-9414-fe72992723c1",modelId:"glm-5v-turbo"};try{var r=document.referrer;if(r){var u=new URL(r);payload.referrerDomain=u.hostname;}}catch(e){}try{var vid=null;try{vid=localStorage.getItem('arena_vid');}catch(e){}if(!vid){vid=typeof crypto!=="undefined"&&crypto.randomUUID?crypto.randomUUID():(Date.now().toString(36)+Math.random().toString(36).slice(2)).slice(0,32);try{localStorage.setItem('arena_vid',vid);}catch(e){}}if(vid)payload.viewerId=vid;}catch(e){}try{fetch("https://www.designarena.ai/api/agon/page-views",{"method":"POST","headers":{"Content-Type":"application/json"},"body":JSON.stringify(payload),"keepalive":true});}catch(e){}})();</script>
</head>
<body>
    <!-- Header -->
    <header class="header" id="header">
        <div class="header-inner">
            <a href="#" class="logo" onclick="showHome()">
                <img src="public/uploads/upload_1.png" alt="9618 Pseudocode Tutor">
            </a>
            <nav class="nav">
                <a href="#topics" class="nav-link active">Topics</a>
                <a href="#compiler" class="nav-link">Compiler</a>
                <a href="#practice" class="nav-link">Practice</a>
                <a href="#papers" class="nav-link">Past Papers</a>
                <a href="#features" class="nav-link">Features</a>
            </nav>
            <div class="nav-actions">
                <button class="btn btn-outline btn-sm" onclick="openModal('login')">Sign In</button>
                <button class="btn btn-primary btn-sm" onclick="openModal('signup')">Get Started</button>
                <button class="mobile-toggle" onclick="toggleMobileMenu()">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Content (shown when not logged in) -->
    <main id="mainContent">
        <!-- Hero Section -->
        <section class="hero">
            <div class="hero-inner">
                <div class="hero-content">
                    <div class="hero-text">
                        <h1>Master <span>CAIE 9618</span> Pseudocode</h1>
                        <p>The complete learning platform for Cambridge International AS & A Level Computer Science Paper 2. Build confidence, practice extensively, and score 65+/75.</p>
                        <div class="hero-buttons">
                            <button class="btn btn-primary" onclick="openModal('signup')">
                                <i class="fas fa-rocket"></i> Start Learning Free
                            </button>
                            <button class="btn btn-outline" onclick="document.getElementById('topics').scrollIntoView({behavior:'smooth'})">
                                <i class="fas fa-book-open"></i> Explore Topics
                            </button>
                        </div>
                        <div class="hero-stats">
                            <div class="stat-item">
                                <strong>14+</strong>
                                <span>Core Topics</span>
                            </div>
                            <div class="stat-item">
                                <strong>200+</strong>
                                <span>Practice Questions</span>
                            </div>
                            <div class="stat-item">
                                <strong>15+</strong>
                                <span>Past Papers</span>
                            </div>
                            <div class="stat-item">
                                <strong>98%</strong>
                                <span>Success Rate</span>
                            </div>
                        </div>
                    </div>
                    <div class="hero-visual">
                        <div class="code-preview">
                            <div class="code-header">
                                <span class="code-dot red"></span>
                                <span class="code-dot yellow"></span>
                                <span class="code-dot green"></span>
                            </div>
                            <div class="code-body">
                                <div><span class="code-comment">// Example: Linear Search</span></div>
                                <div><span class="code-keyword">PROCEDURE</span> <span class="code-function">LinearSearch</span>(Arr, target)</div>
                                <div>&nbsp;&nbsp;<span class="code-keyword">FOR</span> i <span class="code-keyword">FROM</span> <span class="number">0</span> <span class="code-keyword">TO</span> <span class="code-function">LENGTH</span>(Arr) - <span class="number">1</span></div>
                                <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-keyword">IF</span> Arr[i] = target <span class="code-keyword">THEN</span></div>
                                <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-keyword">RETURN</span> i</div>
                                <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-keyword">ENDIF</span></div>
                                <div>&nbsp;&nbsp;<span class="code-keyword">NEXT</span> i</div>
                                <div>&nbsp;&nbsp;<span class="code-keyword">RETURN</span> -<span class="number">1</span></div>
                                <div><span class="code-keyword">ENDPROCEDURE</span></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Topics Section -->
        <section class="section" id="topics">
            <div class="container">
                <div class="section-header fade-in">
                    <span class="section-badge">Complete Syllabus</span>
                    <h2>Paper 2 Fundamentals</h2>
                    <p>Master every concept in the CAIE 9618 syllabus with structured lessons, examples, and interactive practice.</p>
                </div>
                <div class="topics-grid">
                    <div class="topic-card fade-in" onclick="openTopicDetail('variables')">
                        <div class="topic-icon"><i class="fas fa-box"></i></div>
                        <h3>Variables & Constants</h3>
                        <p>Understanding declaration, assignment, naming conventions, and scope of variables and constants.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">12 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('datatypes')">
                        <div class="topic-icon"><i class="fas fa-database"></i></div>
                        <h3>Data Types</h3>
                        <p>INTEGER, REAL, CHAR, BOOLEAN, STRING types and their appropriate usage in pseudocode.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">10 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('operators')">
                        <div class="topic-icon"><i class="fas fa-calculator"></i></div>
                        <h3>Operators</h3>
                        <p>Arithmetic (+,-,*,/,MOD,DIV), relational (<,>,=,<>), and logical (AND,OR,NOT) operators.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">8 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('selection')">
                        <div class="topic-icon"><i class="fas fa-code-branch"></i></div>
                        <h3>Selection</h3>
                        <p>IF...THEN...ELSE, CASE structures for conditional execution and decision making.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">11 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('iteration')">
                        <div class="topic-icon"><i class="fas fa-redo"></i></div>
                        <h3>Iteration</h3>
                        <p>FOR loops, REPEAT...UNTIL, WHILE loops with proper termination conditions.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">13 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('arrays')">
                        <div class="topic-icon"><i class="fas fa-th"></i></div>
                        <h3>Arrays</h3>
                        <p>One-dimensional and two-dimensional arrays, indexing, traversal, and manipulation.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">14 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('strings')">
                        <div class="topic-icon"><i class="fas fa-font"></i></div>
                        <h3>Strings</h3>
                        <p>String operations: concatenation, substring, LENGTH(), character access.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">9 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('procedures')">
                        <div class="topic-icon"><i class="fas fa-cogs"></i></div>
                        <h3>Procedures & Functions</h3>
                        <p>Modular programming: defining, calling procedures and functions with RETURN values.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">15 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('parameters')">
                        <div class="topic-icon"><i class="fas fa-exchange-alt"></i></div>
                        <h3>Parameter Passing</h3>
                        <p>By value vs by reference parameters, understanding side effects and data flow.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">10 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('validation')">
                        <div class="topic-icon"><i class="fas fa-shield-alt"></i></div>
                        <h3>Data Validation</h3>
                        <p>Input validation techniques, range checks, presence checks, type checks.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">8 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('files')">
                        <div class="topic-icon"><i class="fas fa-file-alt"></i></div>
                        <h3>File Handling</h3>
                        <p>OPEN, READ, WRITE, CLOSE files, sequential and random file access.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">11 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('records')">
                        <div class="topic-icon"><i class="fas fa-archive"></i></div>
                        <h3>Records</h3>
                        <p>User-defined data types, record structures, field access and manipulation.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">9 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('tracetables')">
                        <div class="topic-icon"><i class="fas fa-table"></i></div>
                        <h3>Trace Tables</h3>
                        <p>Dry-running algorithms, tracking variable states through program execution.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">12 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                    <div class="topic-card fade-in" onclick="openTopicDetail('logicgates')">
                        <div class="topic-icon"><i class="fas fa-project-diagram"></i></div>
                        <h3>Logic Gates</h3>
                        <p>AND, OR, NOT, NAND, NOR, XOR gates, truth tables, and logic circuits.</p>
                        <div class="topic-meta">
                            <span class="topic-progress">10 Lessons</span>
                            <i class="fas fa-arrow-right topic-arrow"></i>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Features Section -->
        <section class="section" id="features" style="background: var(--bg-white);">
            <div class="container">
                <div class="section-header fade-in">
                    <span class="section-badge">Why Choose Us</span>
                    <h2>Everything You Need to Excel</h2>
                    <p>A complete toolkit designed specifically for Cambridge 9618 Paper 2 success.</p>
                </div>
                <div class="features-grid">
                    <div class="feature-card fade-in">
                        <div class="feature-icon"><i class="fas fa-laptop-code"></i></div>
                        <h3>Live Compiler</h3>
                        <p>Write and test pseudocode instantly with our built-in interpreter. Get real-time feedback on your code.</p>
                    </div>
                    <div class="feature-card fade-in">
                        <div class="feature-icon"><i class="fas fa-robot"></i></div>
                        <h3>PseudoPal AI</h3>
                        <p>Your 24/7 AI tutor that understands every 9618 topic. Ask questions, get explanations, and learn faster.</p>
                    </div>
                    <div class="feature-card fade-in">
                        <div class="feature-icon"><i class="fas fa-tasks"></i></div>
                        <h3>Progress Tracking</h3>
                        <p>Monitor your journey with detailed analytics. Know your strengths and areas needing improvement.</p>
                    </div>
                    <div class="feature-card fade-in">
                        <div class="feature-icon"><i class="fas fa-file-signature"></i></div>
                        <h3>Past Paper Bank</h3>
                        <p>Access years of authentic CAIE past papers with model answers and detailed marking schemes.</p>
                    </div>
                    <div class="feature-card fade-in">
                        <div class="feature-icon"><i class="fas fa-layer-group"></i></div>
                        <h3>Difficulty Levels</h3>
                        <p>Questions tagged Easy, Medium, Hard. Progress naturally from basics to exam-level challenges.</p>
                    </div>
                    <div class="feature-card fade-in">
                        <div class="feature-icon"><i class="fas fa-trophy"></i></div>
                        <h3>Score 65+</h3>
                        <p>Targeted practice designed to help you achieve top marks. Join students who've excelled.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Compiler Section -->
        <section class="compiler-section" id="compiler">
            <div class="section-header fade-in">
                <span class="section-badge" style="background:rgba(37,99,235,0.2);color:#93c5fd;">Interactive Tool</span>
                <h2>Pseudocode Playground</h2>
                <p>Write, run, and debug pseudocode in real-time. Perfect for experimenting and testing your understanding.</p>
            </div>
            <div class="compiler-container fade-in">
                <div class="compiler-tabs">
                    <button class="compiler-tab active" onclick="switchTab(this,'editor')">Code Editor</button>
                    <button class="compiler-tab" onclick="switchTab(this,'examples')">Examples</button>
                    <button class="compiler-tab" onclick="switchTab(this,'reference')">Quick Reference</button>
                </div>
                <div class="compiler-body" id="editorPanel">
                    <div class="editor-panel">
                        <div class="editor-label">Pseudocode Editor</div>
                        <textarea class="code-editor" id="codeEditor" spellcheck="false">// Write your pseudocode here!
// Example: Calculate factorial

DECLARE n : INTEGER
DECLARE result : INTEGER
DECLARE i : INTEGER

OUTPUT "Enter a number: "
INPUT n

result <- 1

FOR i FROM 1 TO n DO
    result <- result * i
NEXT i

OUTPUT "Factorial of ", n, " is ", result</textarea>
                    </div>
                    <div class="output-panel">
                        <div class="output-header">
                            <span class="output-title">Output Console</span>
                            <button class="run-btn" onclick="runCode()">
                                <i class="fas fa-play"></i> Run Code
                            </button>
                        </div>
                        <div class="output-content" id="outputConsole">
                            <div class="output-line info">// Click "Run Code" to execute your pseudocode</div>
                        </div>
                    </div>
                </div>
                <div class="compiler-body" id="examplesPanel" style="display:none;">
                    <div class="editor-panel" style="border:none;">
                        <div class="editor-label">Example Programs</div>
                        <div style="display:flex;flex-direction:column;gap:0.75rem;">
                            <div class="example-item" style="padding:1rem;background:#1e293b;border-radius:var(--radius-md);cursor:pointer;" onclick="loadExample('factorial')">
                                <strong style="color:#60a5fa;">Factorial Calculator</strong>
                                <p style="color:#94a3b8;font-size:0.85rem;margin-top:0.25rem;">Calculate n! using iteration</p>
                            </div>
                            <div class="example-item" style="padding:1rem;background:#1e293b;border-radius:var(--radius-md);cursor:pointer;" onclick="loadExample('bubble')">
                                <strong style="color:#60a5fa;">Bubble Sort</strong>
                                <p style="color:#94a3b8;font-size:0.85rem;margin-top:0.25rem;">Sort an array using bubble sort algorithm</p>
                            </div>
                            <div class="example-item" style="padding:1rem;background:#1e293b;border-radius:var(--radius-md);cursor:pointer;" onclick="loadExample('binarysearch')">
                                <strong style="color:#60a5fa;">Binary Search</strong>
                                <p style="color:#94a3b8;font-size:0.85rem;margin-top:0.25rem;">Search sorted arrays efficiently</p>
                            </div>
                            <div class="example-item" style="padding:1rem;background:#1e293b;border-radius:var(--radius-md);cursor:pointer;" onclick="loadExample('fibonacci')">
                                <strong style="color:#60a5fa;">Fibonacci Sequence</strong>
                                <p style="color:#94a3b8;font-size:0.85rem;margin-top:0.25rem;">Generate Fibonacci numbers</p>
                            </div>
                            <div class="example-item" style="padding:1rem;background:#1e293b;border-radius:var(--radius-md);cursor:pointer;" onclick="loadExample('prime')">
                                <strong style="color:#60a5fa;">Prime Number Check</strong>
                                <p style="color:#94a3b8;font-size:0.85rem;margin-top:0.25rem;">Determine if a number is prime</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="compiler-body" id="referencePanel" style="display:none;">
                    <div class="editor-panel" style="border:none;">
                        <div class="editor-label">CAIE Pseudocode Quick Reference</div>
                        <div style="font-size:0.88rem;line-height:2;color:#e2e8f0;">
                            <table style="width:100%;border-collapse:collapse;">
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>DECLARE</strong> x : INTEGER</td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Declare variable</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>CONSTANT</strong> Max = 100</td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Define constant</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>INPUT</strong> x</td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Read user input</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>OUTPUT</strong> "Text"</td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Display output</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>x &lt;-</strong> 5</td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Assignment</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>IF...THEN...ELSE...ENDIF</strong></td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Conditional</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>FOR...FROM...TO...NEXT</strong></td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Counted loop</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>REPEAT...UNTIL</strong></td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Post-condition loop</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>WHILE...ENDWHILE</strong></td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Pre-condition loop</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>PROCEDURE...ENDPROCEDURE</strong></td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Define procedure</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>FUNCTION...RETURN...ENDFUNCTION</strong></td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Define function</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>CALL</strong> ProcName()</td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Call procedure</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;border-bottom:1px solid #334155;"><strong>RETURN</strong> value</td><td style="color:#94a3b8;padding:0.5rem 0;border-bottom:1px solid #334155;">Return from function</td></tr>
                                <tr><td style="color:#c084fc;padding:0.5rem 0;"><strong>OPEN, READ, WRITE, CLOSE</strong></td><td style="color:#94a3b8;padding:0.5rem 0;">File operations</td></tr>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Practice Section -->
        <section class="section" id="practice">
            <div class="container">
                <div class="section-header fade-in">
                    <span class="section-badge">Test Your Skills</span>
                    <h2>Practice Questions</h2>
                    <p>CAIE-style questions organized by difficulty. Track your progress and build confidence.</p>
                </div>
                <div class="practice-filters fade-in">
                    <button class="filter-btn active" onclick="filterQuestions('all',this)">All Questions</button>
                    <button class="filter-btn easy" onclick="filterQuestions('easy',this)">Easy</button>
                    <button class="filter-btn medium" onclick="filterQuestions('medium',this)">Medium</button>
                    <button class="filter-btn hard" onclick="filterQuestions('hard',this)">Hard</button>
                </div>
                <div class="questions-list" id="questionsList">
                    <div class="question-card fade-in" data-difficulty="easy">
                        <div class="question-header">
                            <span class="question-id">Q001</span>
                            <span class="difficulty-tag easy">Easy</span>
                        </div>
                        <h3>What is the output of this pseudocode?</h3>
                        <div class="code-example">
                            <pre>DECLARE x : INTEGER
x <- 5
x <- x + 3
OUTPUT x</pre>
                        </div>
                        <div class="question-actions">
                            <button class="btn btn-primary btn-sm" onclick="showAnswer(this,'8')">View Answer</button>
                            <button class="btn btn-outline btn-sm">Try Similar</button>
                        </div>
                    </div>
                    <div class="question-card fade-in" data-difficulty="easy">
                        <div class="question-header">
                            <span class="question-id">Q002</span>
                            <span class="difficulty-tag easy">Easy</span>
                        </div>
                        <h3>Identify the data type best suited for storing a student's name.</h3>
                        <div class="question-actions">
                            <button class="btn btn-primary btn-sm" onclick="showAnswer(this,'STRING')">View Answer</button>
                            <button class="btn btn-outline btn-sm">Try Similar</button>
                        </div>
                    </div>
                    <div class="question-card fade-in" data-difficulty="medium">
                        <div class="question-header">
                            <span class="question-id">Q003</span>
                            <span class="difficulty-tag medium">Medium</span>
                        </div>
                        <h3>Trace this loop and determine the final value of sum:</h3>
                        <div class="code-example">
                            <pre>DECLARE sum : INTEGER
sum <- 0
FOR count FROM 1 TO 5 DO
    sum <- sum + count * 2
NEXT count</pre>
                        </div>
                        <div class="question-actions">
                            <button class="btn btn-primary btn-sm" onclick="showAnswer(this,'sum = 30')">View Answer</button>
                            <button class="btn btn-outline btn-sm">Show Trace Table</button>
                        </div>
                    </div>
                    <div class="question-card fade-in" data-difficulty="medium">
                        <div class="question-header">
                            <span class="question-id">Q004</span>
                            <span class="difficulty-tag medium">Medium</span>
                        </div>
                        <h3>What does this procedure do when called with FindMax([3,7,2,9,1])?</h3>
                        <div class="code-example">
                            <pre>PROCEDURE FindMax(Arr)
    DECLARE max : INTEGER
    max <- Arr[0]
    FOR i FROM 1 TO LENGTH(Arr)-1
        IF Arr[i] > max THEN
            max <- Arr[i]
        ENDIF
    NEXT i
    OUTPUT max
ENDPROCEDURE</pre>
                        </div>
                        <div class="question-actions">
                            <button class="btn btn-primary btn-sm" onclick="showAnswer(this,'Outputs: 9 (finds maximum)')">View Answer</button>
                            <button class="btn btn-outline btn-sm">Explain Solution</button>
                        </div>
                    </div>
                    <div class="question-card fade-in" data-difficulty="hard">
                        <div class="question-header">
                            <span class="question-id">Q005</span>
                            <span class="difficulty-tag hard">Hard</span>
                        </div>
                        <h3>Write a function IsPalindrome(word) that returns TRUE if word reads same forwards/backwards.</h3>
                        <p style="color:var(--text-muted);font-size:0.9rem;margin-top:0.5rem;">This is an open-ended coding question worth 6 marks.</p>
                        <div class="question-actions">
                            <button class="btn btn-teal btn-sm"><i class="fas fa-edit"></i> Write Answer</button>
                            <button class="btn btn-outline btn-sm">View Model Answer</button>
                        </div>
                    </div>
                    <div class="question-card fade-in" data-difficulty="hard">
                        <div class="question-header">
                            <span class="question-id">Q006</span>
                            <span class="difficulty-tag hard">Hard</span>
                        </div>
                        <h3>Analyze this recursive function. What is output when called with Mystery(4)?</h3>
                        <div class="code-example">
                            <pre>FUNCTION Mystery(n : INTEGER) : INTEGER
    IF n <= 1 THEN
        RETURN 1
    ELSE
        RETURN n * Mystery(n - 1)
    ENDIF
ENDFUNCTION</pre>
                        </div>
                        <div class="question-actions">
                            <button class="btn btn-primary btn-sm" onclick="showAnswer(this,'Output: 24 (calculates 4! = 4×3×2×1)')">View Answer</button>
                            <button class="btn btn-outline btn-sm">Show Recursion Trace</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Past Papers Section -->
        <section class="section" id="papers" style="background: var(--bg-white);">
            <div class="container">
                <div class="section-header fade-in">
                    <span class="section-badge">Exam Preparation</span>
                    <h2>Past Papers Library</h2>
                    <p>Practice with actual Cambridge examination papers. Model answers included.</p>
                </div>
                <div class="papers-grid">
                    <div class="paper-card fade-in">
                        <div class="paper-year">2024</div>
                        <div class="paper-season">February/March Session</div>
                        <div class="paper-stats">
                            <div class="paper-stat">
                                <strong>75</strong>
                                <span>Total Marks</span>
                            </div>
                            <div class="paper-stat">
                                <strong>6</strong>
                                <span>Questions</span>
                            </div>
                            <div class="paper-stat">
                                <strong>1h 30m</strong>
                                <span>Duration</span>
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width:100%;">
                            <i class="fas fa-file-download"></i> Download Paper
                        </button>
                    </div>
                    <div class="paper-card fade-in">
                        <div class="paper-year">2023</div>
                        <div class="paper-season">October/November Session</div>
                        <div class="paper-stats">
                            <div class="paper-stat">
                                <strong>75</strong>
                                <span>Total Marks</span>
                            </div>
                            <div class="paper-stat">
                                <strong>6</strong>
                                <span>Questions</span>
                            </div>
                            <div class="paper-stat">
                                <strong>1h 30m</strong>
                                <span>Duration</span>
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width:100%;">
                            <i class="fas fa-file-download"></i> Download Paper
                        </button>
                    </div>
                    <div class="paper-card fade-in">
                        <div class="paper-year">2023</div>
                        <div class="paper-season">February/March Session</div>
                        <div class="paper-stats">
                            <div class="paper-stat">
                                <strong>75</strong>
                                <span>Total Marks</span>
                            </div>
                            <div class="paper-stat">
                                <strong>6</strong>
                                <span>Questions</span>
                            </div>
                            <div class="paper-stat">
                                <strong>1h 30m</strong>
                                <span>Duration</span>
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width:100%;">
                            <i class="fas fa-file-download"></i> Download Paper
                        </button>
                    </div>
                    <div class="paper-card fade-in">
                        <div class="paper-year">2022</div>
                        <div class="paper-season">October/November Session</div>
                        <div class="paper-stats">
                            <div class="paper-stat">
                                <strong>75</strong>
                                <span>Total Marks</span>
                            </div>
                            <div class="paper-stat">
                                <strong>6</strong>
                                <span>Questions</span>
                            </div>
                            <div class="paper-stat">
                                <strong>1h 30m</strong>
                                <span>Duration</span>
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width:100%;">
                            <i class="fas fa-file-download"></i> Download Paper
                        </button>
                    </div>
                    <div class="paper-card fade-in">
                        <div class="paper-year">2022</div>
                        <div class="paper-season">February/March Session</div>
                        <div class="paper-stats">
                            <div class="paper-stat">
                                <strong>75</strong>
                                <span>Total Marks</span>
                            </div>
                            <div class="paper-stat">
                                <strong>6</strong>
                                <span>Questions</span>
                            </div>
                            <div class="paper-stat">
                                <strong>1h 30m</strong>
                                <span>Duration</span>
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width:100%;">
                            <i class="fas fa-file-download"></i> Download Paper
                        </button>
                    </div>
                    <div class="paper-card fade-in">
                        <div class="paper-year">2021</div>
                        <div class="paper-season">October/November Session</div>
                        <div class="paper-stats">
                            <div class="paper-stat">
                                <strong>75</strong>
                                <span>Total Marks</span>
                            </div>
                            <div class="paper-stat">
                                <strong>6</strong>
                                <span>Questions</span>
                            </div>
                            <div class="paper-stat">
                                <strong>1h 30m</strong>
                                <span>Duration</span>
                            </div>
                        </div>
                        <button class="btn btn-primary" style="width:100%;">
                            <i class="fas fa-file-download"></i> Download Paper
                        </button>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Dashboard (shown when logged in) -->
    <div class="dashboard" id="dashboard">
        <div class="dashboard-header">
            <div class="dashboard-header-inner">
                <div class="user-avatar"><i class="fas fa-user"></i></div>
                <div class="user-info">
                    <h1>Welcome back, Student!</h1>
                    <p>Continue your 9618 Pseudocode journey</p>
                </div>
            </div>
        </div>
        <div class="dashboard-stats">
            <div class="dash-stat">
                <div class="dash-stat-value">68%</div>
                <div class="dash-stat-label">Overall Progress</div>
            </div>
            <div class="dash-stat">
                <div class="dash-stat-value">142</div>
                <div class="dash-stat-label">Questions Completed</div>
            </div>
            <div class="dash-stat">
                <div class="dash-stat-value">23</div>
                <div class="dash-stat-label">Day Streak 🔥</div>
            </div>
            <div class="dash-stat">
                <div class="dash-stat-value">A*</div>
                <div class="dash-stat-label">Predicted Grade</div>
            </div>
        </div>
        <div class="progress-section">
            <div class="progress-card">
                <h3 style="margin-bottom:1.5rem;">Topic Progress Overview</h3>
                <div class="progress-bar-container">
                    <div class="progress-bar-header">
                        <span>Variables & Constants</span>
                        <span>100%</span>
                    </div>
                    <div class="progress-bar"><div class="progress-fill" style="width:100%"></div></div>
                </div>
                <div class="progress-bar-container">
                    <div class="progress-bar-header">
                        <span>Data Types</span>
                        <span>100%</span>
                    </div>
                    <div class="progress-bar"><div class="progress-fill" style="width:100%"></div></div>
                </div>
                <div class="progress-bar-container">
                    <div class="progress-bar-header">
                        <span>Operators</span>
                        <span>85%</span>
                    </div>
                    <div class="progress-bar"><div class="progress-fill" style="width:85%"></div></div>
                </div>
                <div class="progress-bar-container">
                    <div class="progress-bar-header">
                        <span>Selection</span>
                        <span>90%</span>
                    </div>
                    <div class="progress-bar"><div class="progress-fill" style="width:90%"></div></div>
                </div>
                <div class="progress-bar-container">
                    <div class="progress-bar-header">
                        <span>Iteration</span>
                        <span>75%</span>
                    </div>
                    <div class="progress-bar"><div class="progress-fill" style="width:75%"></div></div>
                </div>
                <div class="progress-bar-container">
                    <div class="progress-bar-header">
                        <span>Arrays</span>
                        <span>60%</span>
                    </div>
                    <div class="progress-bar"><div class="progress-fill" style="width:60%"></div></div>
                </div>
                <div class="progress-bar-container">
                    <div class="progress-bar-header">
                        <span>Procedures & Functions</span>
                        <span>45%</span>
                    </div>
                    <div class="progress-bar"><div class="progress-fill" style="width:45%"></div></div>
                </div>
                <div class="progress-bar-container">
                    <div class="progress-bar-header">
                        <span>File Handling</span>
                        <span>30%</span>
                    </div>
                    <div class="progress-bar"><div class="progress-fill" style="width:30%"></div></div>
                </div>
                <div style="margin-top:2rem;display:flex;gap:1rem;">
                    <button class="btn btn-primary" onclick="document.getElementById('mainContent').style.display='block';document.getElementById('dashboard').classList.remove('active');">
                        <i class="fas fa-book-open"></i> Continue Learning
                    </button>
                    <button class="btn btn-outline" onclick="logout()">
                        <i class="fas fa-sign-out-alt"></i> Logout
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-inner">
            <div class="footer-brand">
                <img src="public/uploads/upload_1.png" alt="9618 Pseudocode Tutor">
                <p>Your complete companion for mastering Cambridge AS & A Level Computer Science Paper 2 pseudocode.</p>
            </div>
            <div class="footer-links">
                <h4>Learning</h4>
                <ul>
                    <li><a href="#topics">All Topics</a></li>
                    <li><a href="#compiler">Code Playground</a></li>
                    <li><a href="#practice">Practice Questions</a></li>
                    <li><a href="#papers">Past Papers</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h4>Resources</h4>
                <ul>
                    <li><a href="#">Syllabus Guide</a></li>
                    <li><a href="#">Quick Reference</a></li>
                    <li><a href="#">Exam Tips</a></li>
                    <li><a href="#">Mark Schemes</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h4>Support</h4>
                <ul>
                    <li><a href="#">Help Center</a></li>
                    <li><a href="#">Contact Us</a></li>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">Terms of Service</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 9618 Pseudocode Tutor. Built for Cambridge International Students.</p>
        </div>
    </footer>

    <!-- Login Modal -->
    <div class="modal-overlay" id="loginModal">
        <div class="modal" style="position:relative;">
            <button class="modal-close" onclick="closeModal('login')">&times;</button>
            <div class="modal-logo">
                <img src="public/uploads/upload_1.png" alt="9618 Pseudocode Tutor">
            </div>
            <h2>Welcome Back</h2>
            <p class="modal-subtitle">Sign in to continue your learning journey</p>
            <form onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label class="form-label">Email Address</label>
                    <input type="email" class="form-input" placeholder="student@example.com" required>
                </div>
                <div class="form-group">
                    <label class="form-label">Password</label>
                    <input type="password" class="form-input" placeholder="Enter your password" required>
                </div>
                <button type="submit" class="btn btn-primary" style="width:100%;">Sign In</button>
            </form>
            <div class="form-divider">or continue with</div>
            <div class="social-auth">
                <button class="btn-social google" onclick="handleGoogleAuth()">
                    <div id="g_id_onload"
     data-client_id="454501645118-0g2nhmpa00vhs5u2innm2lgsljh9gh3c.apps.googleusercontent.com"
     data-callback="handleCredentialResponse">
</div>
<div class="g_id_signin" data-type="standard"></div>

                 </button>
                <button class="btn-social microsoft" onclick="handleMicrosoftAuth()">
                    <i class="fab fa-microsoft"></i> Sign in with Microsoft
                </button>
            </div>
            <div class="modal-footer">
                Don't have an account? <a href="#" onclick="switchModal('signup')">Sign up free</a>
            </div>
        </div>
    </div>

    <!-- Signup Modal -->
    <div class="modal-overlay" id="signupModal">
        <div class="modal" style="position:relative;">
            <button class="modal-close" onclick="closeModal('signup')">&times;</button>
            <div class="modal-logo">
                <img src="public/uploads/upload_1.png" alt="9618 Pseudocode Tutor">
            </div>
            <h2>Create Account</h2>
            <p class="modal-subtitle">Start your 9618 Pseudocode mastery today</p>
            <form onsubmit="handleSignup(event)">
                <div class="form-group">
                    <label class="form-label">Full Name</label>
                    <input type="text" class="form-input" placeholder="Your full name" required>
                </div>
                <div class="form-group">
                    <label class="form-label">Email Address</label>
                    <input type="email" class="form-input" placeholder="student@example.com" required>
                </div>
                <div class="form-group">
                    <label class="form-label">Password</label>
                    <input type="password" class="form-input" placeholder="Create a password" required minlength="8">
                </div>
                <button type="submit" class="btn btn-primary" style="width:100%;">Create Account</button>
            </form>
            <div class="form-divider">or sign up with</div>
            <div class="social-auth">
                <button class="btn-social google" onclick="handleGoogleAuth()">
                    <i class="fab fa-google"></i> Sign up with Google
                </button>
                <button class="btn-social microsoft" onclick="handleMicrosoftAuth()">
                    <i class="fab fa-microsoft"></i> Sign up with Microsoft
                </button>
            </div>
            <div class="modal-footer">
                Already have an account? <a href="#" onclick="switchModal('login')">Sign in</a>
            </div>
        </div>
    </div>

    <!-- Topic Detail Modal -->
    <div class="topic-detail" id="topicDetail">
        <div class="topic-detail-content" id="topicDetailContent">
            <!-- Dynamic content loaded here -->
        </div>
    </div>

    <!-- Chatbot -->
    <div class="chatbot-container">
        <div class="chatbot-window" id="chatbotWindow">
            <div class="chatbot-header">
                <div class="chatbot-avatar"><i class="fas fa-robot"></i></div>
                <div class="chatbot-info">
                    <h4>PseudoPal</h4>
                    <span>9618 Expert AI Tutor</span>
                </div>
            </div>
            <div class="chatbot-messages" id="chatMessages">
                <div class="chat-message bot">
                    👋 Hi there! I'm <strong>PseudoPal</strong>, your AI tutor for Cambridge 9618 Pseudocode. How can I help you today?
                </div>
                <div class="chat-message bot">
                    You can ask me about any topic like:<br><br>
                    • Variables & Data Types<br>
                    • Loops & Selection<br>
                    • Arrays & Strings<br>
                    • Procedures & Functions<br>
                    • File Handling<br>
                    • And much more! 📚
                </div>
            </div>
            <div class="chatbot-input">
                <input type="text" id="chatInput" placeholder="Ask about any 9618 topic..." onkeypress="if(event.key==='Enter')sendMessage()">
                <button class="chatbot-send" onclick="sendMessage()"><i class="fas fa-paper-plane"></i></button>
            </div>
        </div>
        <button class="chatbot-toggle" id="chatbotToggle" onclick="toggleChatbot()">
            <i class="fas fa-comments"></i>
        </button>
    </div>

    <script>
        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Scroll animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

        // Modal functions
        function openModal(type) {
            document.getElementById(type + 'Modal').classList.add('open');
        }

        function closeModal(type) {
            document.getElementById(type + 'Modal').classList.remove('open');
        }

        function switchModal(type) {
            closeModal(type === 'login' ? 'signup' : 'login');
            setTimeout(() => openModal(type), 200);
        }

        // Auth handlers
        function handleLogin(e) {
            e.preventDefault();
            closeModal('login');
            showDashboard();
        }

        function handleSignup(e) {
            e.preventDefault();
            closeModal('signup');
            showDashboard();
        }

        function handleGoogleAuth() {
            // Simulate Google OAuth
            showDashboard();
            closeAllModals();
        }

        function handleMicrosoftAuth() {
            showDashboard();
            closeAllModals();
        }

        function showDashboard() {
            document.getElementById('mainContent').style.display = 'none';
            document.getElementById('dashboard').classList.add('active');
            window.scrollTo(0, 0);
        }

        function showHome() {
            document.getElementById('mainContent').style.display = 'block';
            document.getElementById('dashboard').classList.remove('active');
            window.scrollTo(0, 0);
        }

        function logout() {
            showHome();
        }

        function closeAllModals() {
            document.querySelectorAll('.modal-overlay').forEach(m => m.classList.remove('open'));
        }

        // Compiler functions
        function switchTab(tab, panel) {
            document.querySelectorAll('.compiler-tab').forEach(t => t.classList.remove('active'));
            tab.classList.add('active');
            document.getElementById('editorPanel').style.display = panel === 'editor' ? 'grid' : 'none';
            document.getElementById('examplesPanel').style.display = panel === 'examples' ? 'grid' : 'none';
            document.getElementById('referencePanel').style.display = panel === 'reference' ? 'grid' : 'none';
        }

        function runCode() {
            const code = document.getElementById('codeEditor').value;
            const output = document.getElementById('outputConsole');
            output.innerHTML = '<div class="output-line info">▶ Running pseudocode...</div>';
            
            setTimeout(() => {
                try {
                    const result = interpretPseudocode(code);
                    output.innerHTML = result.map(r => 
                        `<div class="output-line ${r.type}">${r.text}</div>`
                    ).join('');
                } catch (err) {
                    output.innerHTML += `<div class="output-line error">⚠ Error: ${err.message}</div>`;
                }
            }, 300);
        }

        function interpretPseudocode(code) {
            const results = [];
            const lines = code.split('\n');
            const variables = {};
            
            for (let line of lines) {
                line = line.trim();
                
                // Skip comments
                if (line.startsWith('//')) continue;
                
                // DECLARE statements
                const declareMatch = line.match(/DECLARE\s+(\w+)\s*:\s*(INTEGER|REAL|STRING|CHAR|BOOLEAN)/i);
                if (declareMatch) {
                    variables[declareMatch[1]] = declareMatch[2] === 'STRING' ? '' : 0;
                    results.push({ type: 'info', text: `Declared ${declareMatch[1]} as ${declareMatch[2]}` });
                    continue;
                }
                
                // Assignment
                const assignMatch = line.match(/(\w+)\s*<-\s*(.+)$/);
                if (assignMatch) {
                    const varName = assignMatch[1];
                    let value = assignMatch[2].trim();
                    
                    // Evaluate expression
                    try {
                        value = evaluateExpression(value, variables);
                    } catch(e) {}
                    
                    variables[varName] = value;
                    results.push({ type: 'info', text: `${varName} ← ${value}` });
                    continue;
                }
                
                // OUTPUT
                const outputMatch = line.match(/OUTPUT\s+(.+)/i);
                if (outputMatch) {
                    let text = outputMatch[1];
                    // Replace variables
                    Object.keys(variables).forEach(v => {
                        text = text.replace(new RegExp('\\b' + v + '\\b', 'g'), variables[v]);
                    });
                    // Remove quotes from strings
                    text = text.replace(/"/g, '');
                    results.push({ type: 'success', text: `>> ${text}` });
                    continue;
                }
                
                // INPUT
                const inputMatch = line.match(/INPUT\s+(\w+)/i);
                if (inputMatch) {
                    const simulatedInput = Math.floor(Math.random() * 100);
                    variables[inputMatch[1]] = simulatedInput;
                    results.push({ type: 'info', text: `[Input] ${inputMatch[1]} ← ${simulatedInput} (simulated)` });
                    continue;
                }
                
                // FOR loop (basic)
                const forMatch = line.match(/FOR\s+(\w+)\s+FROM\s+(\d+)\s+TO\s+(\d+)\s*DO/i);
                if (forMatch) {
                    const loopVar = forMatch[1];
                    const start = parseInt(forMatch[2]);
                    const end = parseInt(forMatch[3]);
                    results.push({ type: 'info', text: `Loop: ${loopVar} from ${start} to ${end}` });
                    continue;
                }
                
                // NEXT
                if (line.match(/^NEXT\s/i)) {
                    continue;
                }
                
                // IF/THEN/ELSE/ENDIF
                if (line.match(/^(IF|ELSE|THEN|ENDIF|ENDWHILE|ENDFOR|REPEAT|UNTIL|WHILE|DO|CASE|OF|OTHERWISE|ENDCASE)/i)) {
                    continue;
                }
            }
            
            if (results.length <= 1) {
                results.push({ type: 'success', text: '✓ Program executed successfully' });
            }
            
            return results;
        }

        function evaluateExpression(expr, vars) {
            expr = expr.trim();
            
            // Replace variables
            Object.keys(vars).forEach(v => {
                expr = expr.replace(new RegExp('\\b' + v + '\\b', 'g'), vars[v]);
            });
            
            // Remove string quotes
            if (expr.startsWith('"') && expr.endsWith('"')) {
                return expr.slice(1, -1);
            }
            
            // Handle arithmetic
            try {
                // Simple arithmetic evaluation
                if (/^[\d\s+\-*/().]+$/.test(expr)) {
                    return eval(expr);
                }
            } catch(e) {}
            
            return expr;
        }

        // Example code snippets
        const examples = {
            factorial: `// Factorial Calculator
DECLARE n : INTEGER
DECLARE result : INTEGER
DECLARE i : INTEGER

OUTPUT "Enter a number: "
INPUT n

result <- 1

FOR i FROM 1 TO n DO
    result <- result * i
NEXT i

OUTPUT "Factorial of "
OUTPUT n
OUTPUT " is "
OUTPUT result`,
            bubble: `// Bubble Sort Algorithm
DECLARE arr : ARRAY[0..4] OF INTEGER
DECLARE temp : INTEGER
DECLARE i : INTEGER
DECLARE j : INTEGER

// Initialize array
arr[0] <- 64
arr[1] <- 34
arr[2] <- 25
arr[3] <- 12
arr[4] <- 22

// Bubble sort
FOR i FROM 0 TO 4 DO
    FOR j FROM 0 TO 3 DO
        IF arr[j] > arr[j+1] THEN
            temp <- arr[j]
            arr[j] <- arr[j+1]
            arr[j+1] <- temp
        ENDIF
    NEXT j
NEXT i

OUTPUT "Sorted array: "
OUTPUT arr[0], arr[1], arr[2], arr[3], arr[4]`,
            binarysearch: `// Binary Search
DECLARE arr : ARRAY[0..9] OF INTEGER
DECLARE target : INTEGER
DECLARE low : INTEGER
DECLARE high : INTEGER
DECLARE mid : INTEGER

// Sorted array
arr[0] <- 2
arr[1] <- 5
arr[2] <- 8
arr[3] <- 12
arr[4] <- 16
arr[5] <- 23
arr[6] <- 38
arr[7] <- 45
arr[8] <- 56
arr[9] <- 72

target <- 23
low <- 0
high <- 9

WHILE low <= high DO
    mid <- (low + high) DIV 2
    
    IF arr[mid] = target THEN
        OUTPUT "Found at index: "
        OUTPUT mid
        EXIT
    ELSE
        IF arr[mid] < target THEN
            low <- mid + 1
        ELSE
            high <- mid - 1
        ENDIF
    ENDIF
ENDWHILE`,
            fibonacci: `// Fibonacci Sequence Generator
DECLARE n : INTEGER
DECLARE first : INTEGER
DECLARE second : INTEGER
DECLARE next : INTEGER
DECLARE i : INTEGER

OUTPUT "How many terms? "
INPUT n

first <- 0
second <- 1

OUTPUT "Fibonacci sequence:"
OUTPUT first
OUTPUT second

FOR i FROM 3 TO n DO
    next <- first + second
    OUTPUT next
    first <- second
    second <- next
NEXT i`,
            prime: `// Prime Number Checker
DECLARE num : INTEGER
DECLARE isPrime : BOOLEAN
DECLARE i : INTEGER

OUTPUT "Enter a number: "
INPUT num

isPrime <- TRUE

IF num < 2 THEN
    isPrime <- FALSE
ELSE
    FOR i FROM 2 TO num - 1 DO
        IF num MOD i = 0 THEN
            isPrime <- FALSE
        ENDIF
    NEXT i
ENDIF

IF isPrime = TRUE THEN
    OUTPUT num, " is prime"
ELSE
    OUTPUT num, " is not prime"
ENDIF`
        };

        function loadExample(name) {
            document.getElementById('codeEditor').value = examples[name];
            switchTab(document.querySelector('.compiler-tab'), 'editor');
        }

        // Question filters
        function filterQuestions(difficulty, btn) {
            document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            
            document.querySelectorAll('.question-card').forEach(card => {
                if (difficulty === 'all' || card.dataset.difficulty === difficulty) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        function showAnswer(btn, answer) {
            const card = btn.closest('.question-card');
            let answerDiv = card.querySelector('.answer-display');
            if (!answerDiv) {
                answerDiv = document.createElement('div');
                answerDiv.className = 'answer-display';
                answerDiv.style.cssText = 'margin-top:1rem;padding:1rem;background:#f0fdfa;border-radius:var(--radius-sm);border-left:4px solid var(--teal);color:#0f766e;';
                card.appendChild(answerDiv);
            }
            answerDiv.innerHTML = '<strong>✓ Answer:</strong> ' + answer;
            btn.textContent = 'Answer Shown';
            btn.disabled = true;
            btn.style.opacity = '0.7';
        }

        // Topic detail content
        const topicDetails = {
            variables: {
                icon: 'fa-box',
                title: 'Variables & Constants',
                desc: 'Understanding how to store and manipulate data in pseudocode',
                concepts: [
                    {
                        title: 'What are Variables?',
                        content: 'A variable is a named storage location in memory that holds a value which can change during program execution. In CAIE pseudocode, variables must be declared before use.',
                        code: `DECLARE score : INTEGER
DECLARE name : STRING
DECLARE price : REAL`
                    },
                    {
                        title: 'What are Constants?',
                        content: 'A constant is a named value that cannot change during program execution. Use constants for fixed values like PI, MAX_SIZE, or tax rates.',
                        code: `CONSTANT PI = 3.14159
CONSTANT MAX_STUDENTS = 30
CONSTANT PASS_MARK = 50`
                    },
                    {
                        title: 'Assignment Operator',
                        content: 'The arrow operator (<-) assigns values to variables. The right side is evaluated first, then stored in the left-side variable.',
                        code: `DECLARE x : INTEGER
x <- 10          // x now holds 10
x <- x + 5       // x now holds 15
name <- "Alice"  // name now holds "Alice"`
                    }
                ]
            },
            datatypes: {
                icon: 'fa-database',
                title: 'Data Types',
                desc: 'Understanding different types of data in pseudocode',
                concepts: [
                    {
                        title: 'Integer (INTEGER)',
                        content: 'Whole numbers without decimal points. Used for counting, indexing, and discrete values.',
                        code: `DECLARE age : INTEGER
DECLARE count : INTEGER
age <- 17
count <- 42`
                    },
                    {
                        title: 'Real (REAL)',
                        content: 'Numbers with decimal points. Used for measurements, calculations requiring precision.',
                        code: `DECLARE temperature : REAL
DECLARE average : REAL
temperature <- 36.6
average <- 78.5`
                    },
                    {
                        title: 'String (STRING)',
                        content: 'Sequences of characters enclosed in quotes. Used for text data.',
                        code: `DECLARE name : STRING
DECLARE message : STRING
name <- "John Smith"
message <- "Hello, World!"`
                    },
                    {
                        title: 'Boolean (BOOLEAN)',
                        content: 'Can only hold TRUE or FALSE values. Used for flags and conditions.',
                        code: `DECLARE isValid : Boolean
DECLARE found : Boolean
isValid <- TRUE
found <- FALSE`
                    }
                ]
            },
            selection: {
                icon: 'fa-code-branch',
                title: 'Selection Structures',
                desc: 'Making decisions in your programs using IF and CASE statements',
                concepts: [
                    {
                        title: 'IF...THEN...ENDIF',
                        content: 'Basic conditional execution. Code inside runs only if condition is true.',
                        code: `DECLARE grade : INTEGER
grade <- 75

IF grade >= 50 THEN
    OUTPUT "Pass!"
ENDIF`
                    },
                    {
                        title: 'IF...THEN...ELSE...ENDIF',
                        content: 'Two-way choice. One block runs if true, another if false.',
                        code: `DECLARE mark : INTEGER
mark <- 45

IF mark >= 50 THEN
    OUTPUT "Pass"
ELSE
    OUTPUT "Fail"
ENDIF`
                    },
                    {
                        title: 'Nested IF Statements',
                        content: 'IF statements inside other IF statements for complex decisions.',
                        code: `DECLARE score : INTEGER
score <- 78

IF score >= 70 THEN
    OUTPUT "Grade A"
ELSE
    IF score >= 60 THEN
        OUTPUT "Grade B"
    ELSE
        OUTPUT "Grade C or below"
    ENDIF
ENDIF`
                    },
                    {
                        title: 'CASE Statement',
                        content: 'Multi-way selection based on a single variable value.',
                        code: `DECLARE day : INTEGER
day <- 3

CASE OF day
    1 : OUTPUT "Monday"
    2 : OUTPUT "Tuesday"
    3 : OUTPUT "Wednesday"
    4 : OUTPUT "Thursday"
    5 : OUTPUT "Friday"
    OTHERWISE : OUTPUT "Weekend"
ENDCASE`
                    }
                ]
            },
            iteration: {
                icon: 'fa-redo',
                title: 'Iteration (Loops)',
                desc: 'Repeating blocks of code efficiently',
                concepts: [
                    {
                        title: 'FOR Loop',
                        content: 'Count-controlled loop. Runs a specific number of times.',
                        code: `DECLARE i : INTEGER

FOR i FROM 1 TO 5 DO
    OUTPUT "Count: ", i
NEXT i
// Output: Count: 1, 2, 3, 4, 5`
                    },
                    {
                        title: 'REPEAT...UNTIL Loop',
                        content: 'Post-condition loop. Runs at least once, continues until condition is true.',
                        code: `DECLARE total : INTEGER
total <- 0

REPEAT
    total <- total + 1
    OUTPUT "Total: ", total
UNTIL total >= 3`
                    },
                    {
                        title: 'WHILE Loop',
                        content: 'Pre-condition loop. May not run at all if condition is initially false.',
                        code: `DECLARE count : INTEGER
count <- 5

WHILE count > 0 DO
    OUTPUT count
    count <- count - 1
ENDWHILE
// Output: 5, 4, 3, 2, 1`
                    }
                ]
            },
            arrays: {
                icon: 'fa-th',
                title: 'Arrays',
                desc: 'Storing multiple values of the same type',
                concepts: [
                    {
                        title: 'Declaring Arrays',
                        content: 'Arrays store multiple values under one name, accessed by index starting from 0.',
                        code: `DECLARE scores : ARRAY[0..4] OF INTEGER
DECLARE names : ARRAY[0..2] OF STRING`
                    },
                    {
                        title: 'Accessing Array Elements',
                        content: 'Use square brackets with index to read or modify elements.',
                        code: `scores[0] <- 85
scores[1] <- 92
scores[2] <- 78
scores[3] <- 95
scores[4] <- 88

OUTPUT scores[2]  // Outputs: 78`
                    },
                    {
                        title: 'Traversing Arrays',
                        content: 'Use loops to process each element in an array.',
                        code: `DECLARE i : INTEGER
DECLARE sum : INTEGER
sum <- 0

FOR i FROM 0 TO 4 DO
    sum <- sum + scores[i]
NEXT i

OUTPUT "Total: ", sum`
                    }
                ]
            },
            operators: {
                icon: 'fa-calculator',
                title: 'Operators',
                desc: 'Performing calculations and comparisons',
                concepts: [
                    {
                        title: 'Arithmetic Operators',
                        content: '+, -, *, / for basic math. MOD gives remainder, DIV gives integer division.',
                        code: `DECLARE a : INTEGER
a <- 17 DIV 5     // a = 3
a <- 17 MOD 5     // a = 2
a <- 10 + 3 * 2   // a = 16 (BODMAS)`
                    },
                    {
                        title: 'Relational Operators',
                        content: 'Compare values: = (equal), <> (not equal), <, >, <=, >=' ,
                        code: `IF x > y THEN ...
IF score <> -1 THEN ...
IF age >= 18 THEN ...`
                    },
                    {
                        title: 'Logical Operators',
                        content: 'AND, OR, NOT for combining boolean expressions.',
                        code: `IF age >= 18 AND hasID = TRUE THEN ...
IF grade = "A" OR grade = "B" THEN ...
IF NOT found THEN ...`
                    }
                ]
            },
            strings: {
                icon: 'fa-font',
                title: 'Strings',
                desc: 'Working with text data',
                concepts: [
                    {
                        title: 'String Basics',
                        content: 'Strings are sequences of characters enclosed in double quotes.',
                        code: `DECLARE name : STRING
name <- "Cambridge"
OUTPUT name  // Outputs: Cambridge`
                    },
                    {
                        title: 'String Operations',
                        content: 'Concatenation with +, LENGTH() function, character access with [].',
                        code: `DECLARE firstName : STRING
DECLARE lastName : STRING
DECLARE fullName : STRING

firstName <- "Alan"
lastName <- "Turing"
fullName <- firstName + " " + lastName
// fullName = "Alan Turing"

OUTPUT LENGTH(fullName)  // Outputs: 12`
                    }
                ]
            },
            procedures: {
                icon: 'fa-cogs',
                title: 'Procedures & Functions',
                desc: 'Modular programming with reusable code blocks',
                concepts: [
                    {
                        title: 'Procedures',
                        content: 'A named block of code that performs a task. Called using CALL statement.',
                        code: `PROCEDURE Greet(name : STRING)
    OUTPUT "Hello, " + name + "!"
ENDPROCEDURE

CALL Greet("Student")
// Output: Hello, Student!`
                    },
                    {
                        title: 'Functions',
                        content: 'Like procedures but RETURN a value. Can be used in expressions.',
                        code: `FUNCTION Square(n : INTEGER) : INTEGER
    DECLARE result : INTEGER
    result <- n * n
    RETURN result
ENDFUNCTION

DECLARE x : INTEGER
x <- Square(5)
OUTPUT x  // Output: 25`
                    }
                ]
            },
            parameters: {
                icon: 'fa-exchange-alt',
                title: 'Parameter Passing',
                desc: 'How data flows into and out of subprograms',
                concepts: [
                    {
                        title: 'By Value',
                        content: 'A copy of the value is passed. Changes inside don\'t affect original.',
                        code: `PROCEDURE Double(x : INTEGER)
    x <- x * 2
    OUTPUT x
ENDPROCEDURE

DECLARE num : INTEGER
num <- 5
CALL Double(num)
OUTPUT num  // Still 5 (unchanged)`
                    },
                    {
                        title: 'By Reference',
                        content: 'Reference to original variable passed. Changes affect original.',
                        code: `PROCEDURE Double(REF x : INTEGER)
    x <- x * 2
ENDPROCEDURE

DECLARE num : INTEGER
num <- 5
CALL Double(num)
OUTPUT num  // Now 10 (changed!)`
                    }
                ]
            },
            validation: {
                icon: 'fa-shield-alt',
                title: 'Data Validation',
                desc: 'Ensuring user input is correct and safe',
                concepts: [
                    {
                        title: 'Range Check',
                        content: 'Verify input falls within acceptable bounds.',
                        code: `DECLARE age : INTEGER
REPEAT
    OUTPUT "Enter age (0-120): "
    INPUT age
UNTIL age >= 0 AND age <= 120`
                    },
                    {
                        title: 'Presence Check',
                        content: 'Ensure a value has been entered (not empty).',
                        code: `DECLARE name : STRING
REPEAT
    OUTPUT "Enter name: "
    INPUT name
UNTIL LENGTH(name) > 0`
                    },
                    {
                        title: 'Type Check',
                        content: 'Verify input matches expected data type.',
                        code: `// In pseudocode, we assume INPUT handles
// basic type checking based on declared type
DECLARE score : INTEGER
OUTPUT "Enter integer score: "
INPUT score  // Will be validated as INTEGER`
                    }
                ]
            },
            files: {
                icon: 'fa-file-alt',
                title: 'File Handling',
                desc: 'Reading from and writing to external files',
                concepts: [
                    {
                        title: 'Opening Files',
                        content: 'Use OPEN command with filename and mode (READ/WRITE/APPEND).',
                        code: `DECLARE myFile : FILE
OPEN myFile FOR READ "data.txt"
OPEN myFile FOR WRITE "output.txt"`
                    },
                    {
                        title: 'Reading Files',
                        content: 'Read data sequentially from opened file.',
                        code: `DECLARE line : STRING
OPEN myFile FOR READ "students.txt"

READ myFile, line
OUTPUT line

CLOSE myFile`
                    },
                    {
                        title: 'Writing Files',
                        content: 'Write data to external files for persistent storage.',
                        code: `DECLARE myFile : FILE
OPEN myFile FOR WRITE "results.txt"

WRITE myFile, "Student Name: Alice"
WRITE myFile, "Score: 95"

CLOSE myFile`
                    }
                ]
            },
            records: {
                icon: 'fa-archive',
                title: 'Records',
                desc: 'User-defined composite data types',
                concepts: [
                    {
                        title: 'Defining Records',
                        content: 'Create custom data types grouping related fields together.',
                        code: `TYPE StudentRecord
    DECLARE name : STRING
    DECLARE age : INTEGER
    DECLARE grade : CHAR
ENDTYPE

DECLARE student : StudentRecord`
                    },
                    {
                        title: 'Accessing Record Fields',
                        content: 'Use dot notation to access individual fields.',
                        code: `student.name <- "Bob Smith"
student.age <- 17
student.grade <- "A"

OUTPUT student.name
OUTPUT student.age`
                    }
                ]
            },
            tracetables: {
                icon: 'fa-table',
                title: 'Trace Tables',
                desc: 'Tracking variable values during program execution',
                concepts: [
                    {
                        title: 'Creating Trace Tables',
                        content: 'Track each variable\'s value after every line executes.',
                        code: `// Code to trace:
DECLARE x : INTEGER
DECLARE y : INTEGER
x <- 5
y <- x + 3
x <- y * 2

// Trace Table:
// Line   | x  | y
// -----------------
// x<-5   | 5  | -
// y<-x+3 | 5  | 8
// x<-y*2 | 16 | 8`
                    }
                ]
            },
            logicgates: {
                icon: 'fa-project-diagram',
                title: 'Logic Gates',
                desc: 'Digital logic fundamentals for computer science',
                concepts: [
                    {
                        title: 'Basic Logic Gates',
                        content: 'AND, OR, NOT form the foundation of digital logic circuits.',
                        code: `// Truth Table: AND Gate
// A | B | Output
// --------------
// 0 | 0 |   0
// 0 | 1 |   0
// 1 | 0 |   0
// 1 | 1 |   1

// Truth Table: OR Gate
// A | B | Output
// --------------
// 0 | 0 |   0
// 0 | 1 |   1
// 1 | 0 |   1
// 1 | 1 |   1`
                    }
                ]
            }
        };

        function openTopicDetail(topicId) {
            const topic = topicDetails[topicId];
            if (!topic) return;

            const content = document.getElementById('topicDetailContent');
            content.innerHTML = `
                <button class="close-detail" onclick="closeTopicDetail()">&times;</button>
                <div class="topic-detail-header">
                    <div class="topic-detail-icon"><i class="fas ${topic.icon}"></i></div>
                    <div>
                        <h2>${topic.title}</h2>
                        <p>${topic.desc}</p>
                    </div>
                </div>
                ${topic.concepts.map(c => `
                    <div class="concept-block">
                        <h3>${c.title}</h3>
                        <p>${c.content}</p>
                        <div class="code-example"><pre>${c.code}</pre></div>
                    </div>
                `).join('')}
                <div style="margin-top:2rem;display:flex;gap:1rem;">
                    <button class="btn btn-primary" onclick="closeTopicDetail();document.getElementById('practice').scrollIntoView({behavior:'smooth'});">
                        <i class="fas fa-pencil-alt"></i> Practice This Topic
                    </button>
                    <button class="btn btn-outline" onclick="closeTopicDetail();document.getElementById('compiler').scrollIntoView({behavior:'smooth'});">
                        <i class="fas fa-code"></i> Try in Compiler
                    </button>
                </div>
            `;
            document.getElementById('topicDetail').classList.add('open');
        }

        function closeTopicDetail() {
            document.getElementById('topicDetail').classList.remove('open');
        }

        // Close modals on overlay click
        document.querySelectorAll('.modal-overlay, .topic-detail').forEach(overlay => {
            overlay.addEventListener('click', (e) => {
                if (e.target === overlay) {
                    overlay.classList.remove('open');
                }
            });
        });

        // Chatbot functionality
        function toggleChatbot() {
            const window = document.getElementById('chatbotWindow');
            window.classList.toggle('open');
        }

        function sendMessage() {
            const input = document.getElementById('chatInput');
            const message = input.value.trim();
            if (!message) return;

            const messagesContainer = document.getElementById('chatMessages');
            
            // Add user message
            messagesContainer.innerHTML += `<div class="chat-message user">${message}</div>`;
            input.value = '';
            
            // Generate AI response
            setTimeout(() => {
                const response = generateResponse(message);
                messagesContainer.innerHTML += `<div class="chat-message bot">${response}</div>`;
                messagesContainer.scrollTop = messagesContainer.scrollHeight;
            }, 500 + Math.random() * 500);
            
            messagesContainer.scrollTop = messagesContainer.scrollHeight;
        }

        function generateResponse(message) {
            const msg = message.toLowerCase();
            
            if (msg.includes('variable') || msg.includes('declare')) {
                return `📦 <strong>Variables in 9618 Pseudocode:</strong><br><br>
                Variables are declared using the <code>DECLARE</code> keyword:<br><br>
                <code>DECLARE name : DATATYPE</code><br><br>
                Common data types: <strong>INTEGER</strong>, <strong>REAL</strong>, <strong>STRING</strong>, <strong>BOOLEAN</strong>, <strong>CHAR</strong>.<br><br>
                Values are assigned using <code>&lt;-</code> operator.<br><br>
                Want me to explain constants too? 😊`;
            }
            
            if (msg.includes('loop') || msg.includes('iteration') || msg.includes('for') || msg.includes('while')) {
                return `🔄 <strong>Loops in 9618 Pseudocode:</strong><br><br>
                There are <strong>three main loop types</strong>:<br><br>
                1️⃣ <strong>FOR loop</strong> - Counted iterations<br>
                <code>FOR i FROM 1 TO 10 DO ... NEXT i</code><br><br>
                2️⃣ <strong>WHILE loop</strong> - Pre-condition<br>
                <code>WHILE condition DO ... ENDWHILE</code><br><br>
                3️⃣ <strong>REPEAT loop</strong> - Post-condition<br>
                <code>REPEAT ... UNTIL condition</code><br><br>
                Need examples for any specific loop? 🎯`;
            }
            
            if (msg.includes('array') || msg.includes('array')) {
                return `🔲 <strong>Arrays in 9618 Pseudocode:</strong><br><br>
                Arrays store multiple values of the same type:<br><br>
                <code>DECLARE arr : ARRAY[0..4] OF INTEGER</code><br><br>
                Key points:<br>
                • Index starts at <strong>0</strong><br>
                • Access: <code>arr[0]</code>, <code>arr[1]</code>, etc.<br>
                • Use <code>LENGTH(arr)</code> for size<br>
                • 2D arrays: <code>ARRAY[0..2][0..3]</code><br><br>
                Want to see array traversal examples? 📚`;
            }
            
            if (msg.includes('function') || msg.includes('procedure') || msg.includes('parameter')) {
                return `⚙️ <strong>Procedures & Functions:</strong><br><br>
                <strong>Procedures</strong> perform tasks:<br>
                <code>PROCEDURE Name(params)<br>...<br>ENDPROCEDURE</code><br><br>
                <strong>Functions</strong> return values:<br>
                <code>FUNCTION Name(params) : ReturnType<br>...<br>RETURN value<br>ENDFUNCTION</code><br><br>
                Parameters can pass <strong>by value</strong> (copy) or <strong>by reference</strong> (original) using <code>REF</code>.<br><br>
                Need more details? 💡`;
            }
            
            if (msg.includes('selection') || msg.includes('if') || msg.includes('else') || msg.includes('case')) {
                return `🔀 <strong>Selection Structures:</strong><br><br>
                <strong>IF statement:</strong><br>
                <code>IF condition THEN<br>&nbsp;&nbsp;// code<br>ENDIF</code><br><br>
                <strong>IF-ELSE:</strong><br>
                <code>IF condition THEN<br>&nbsp;&nbsp;// true case<br>ELSE<br>&nbsp;&nbsp;// false case<br>ENDIF</code><br><br>
                <strong>CASE statement:</strong><br>
                <code>CASE OF variable<br>&nbsp;&nbsp;value1 : action1<br>&nbsp;&nbsp;value2 : action2<br>&nbsp;&nbsp;OTHERWISE : default<br>ENDCASE</code><br><br>
                Clear enough? ✨`;
            }
            
            if (msg.includes('hello') || msg.includes('hi') || msg.includes('hey')) {
                return `Hello! 👋 Great to meet you!<br><br>I'm <strong>PseudoPal</strong>, your expert tutor for Cambridge 9618 Computer Science Paper 2.<br><br>You can ask me about ANY topic from the syllabus:<br>
• Variables & Data Types<br>
• Operators & Expressions<br>
• Selection & Iteration<br>
• Arrays & Strings<br>
• Procedures & Functions<br>
• File Handling<br>
• Validation<br>
• Trace Tables<br><br>What would you like to learn? 🚀`;
            }
            
            if (msg.includes('exam') || msg.includes('paper') || msg.includes('mark') || msg.includes('score')) {
                return `📝 <strong>Exam Tips for 9618 Paper 2:</strong><br><br>
                • Total marks: <strong>75</strong> over 1 hour 30 minutes<br>
• Aim for <strong>65+/75</strong> for an A/A* grade<br>
• Always <strong>declare variables</strong> before use<br>
• Use correct <strong>pseudocode syntax</strong> exactly<br>
• Show <strong>trace tables</strong> clearly with columns<br>
• For functions, always include <strong>RETURN</strong><br>
• Check <strong>boundary conditions</strong> in loops<br><br>
                Need help with specific question types? 🎯`;
            }
            
            if (msg.includes('thank') || msg.includes('thanks')) {
                return `You're welcome! 😊<br><br>Keep practicing and you'll ace Paper 2! Remember: consistency beats intensity. Even 15 minutes daily makes a huge difference.<br><br>Good luck with your studies! 🌟`;
            }
            
            // Default response
            return `Great question! 🤔<br><br>
            I can help you with any 9618 Paper 2 topic. Here's what I know well:<br><br>
            📦 Variables & Constants<br>
            🔢 Data Types & Operators<br>
            🔀 Selection (IF/CASE)<br>
            🔄 Iteration (Loops)<br>
            🔲 Arrays & Strings<br>
            ⚙️ Procedures & Functions<br>
            📁 File Handling<br>
            ✅ Data Validation<br>
            📊 Trace Tables<br><br>
            Could you tell me more specifically what you'd like to understand? 💡`;
        }

        // Mobile menu toggle
        function toggleMobileMenu() {
            const nav = document.querySelector('.nav');
            nav.style.display = nav.style.display === 'flex' ? 'none' : 'flex';
            nav.style.position = 'absolute';
            nav.style.top = '100%';
            nav.style.left = '0';
            nav.style.right = '0';
            nav.style.background = 'white';
            nav.style.flexDirection = 'column';
            nav.style.padding = '1rem';
            nav.style.boxShadow = 'var(--shadow-lg)';
            nav.style.borderRadius = '0 0 var(--radius-lg) var(--radius-lg)';
        }

        // Smooth scroll for nav links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Initialize
        console.log('9618 Pseudocode Tutor loaded successfully!');
    </script>
</body>
</html>
