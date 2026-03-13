<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Claudio Giordani - Executive CV</title>
    <style>
        /* Color Variables for Theming */
        :root {
            --bg-color: #f4f7f6;
            --text-main: #2d3436;
            --text-muted: #636e72;
            --card-bg: #ffffff;
            --accent: #0984e3;
            --border: #dfe6e9;
        }

        [data-theme="dark"] {
            --bg-color: #0f172a;
            --text-main: #f1f5f9;
            --text-muted: #94a3b8;
            --card-bg: #1e293b;
            --accent: #38bdf8;
            --border: #334155;
        }

        /* Global Styles */
        body {
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            margin: 0;
            padding: 0;
            line-height: 1.6;
            transition: background-color 0.3s, color 0.3s;
        }

        /* Dark Mode Toggle Switch */
        .theme-switch-wrapper {
            position: fixed;
            top: 20px;
            right: 20px;
            display: flex;
            align-items: center;
            z-index: 100;
            background: var(--card-bg);
            padding: 8px 15px;
            border-radius: 30px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            border: 1px solid var(--border);
        }
        .theme-switch { display: none; }
        .theme-switch-label {
            cursor: pointer;
            font-size: 0.9em;
            font-weight: 600;
            color: var(--text-main);
            user-select: none;
        }

        /* Dashboard Layout */
        .dashboard {
            max-width: 1200px;
            margin: 60px auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: 320px 1fr;
            gap: 40px;
        }

        /* Sticky Sidebar */
        .sidebar {
            position: sticky;
            top: 60px;
            height: fit-content;
        }

        .profile-card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 16px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
            border: 1px solid var(--border);
            transition: background-color 0.3s, border-color 0.3s;
        }

        h1 { margin: 0 0 5px 0; font-size: 2.2em; line-height: 1.1; color: var(--text-main); }
        .title { color: var(--accent); font-weight: 600; font-size: 1.1em; margin-bottom: 20px; }
        
        .contact-list { list-style: none; padding: 0; margin: 0 0 20px 0; color: var(--text-muted); font-size: 0.95em; }
        .contact-list li { margin-bottom: 10px; }
        .contact-list a { color: var(--accent); text-decoration: none; font-weight: 500; }
        .contact-list a:hover { text-decoration: underline; }

        .skills-section h3 { margin-bottom: 10px; border-bottom: 1px solid var(--border); padding-bottom: 5px; color: var(--text-main); }
        .skill-tags { display: flex; flex-wrap: wrap; gap: 8px; }
        .tag { background: var(--bg-color); color: var(--text-main); padding: 5px 12px; border-radius: 8px; font-size: 0.85em; border: 1px solid var(--border); }

        /* Main Content Timeline */
        h2 { color: var(--text-main); font-size: 1.8em; margin-top: 0; margin-bottom: 20px; display: flex; align-items: center; gap: 10px; }
        
        .intro-text { font-size: 1.05em; margin-bottom: 40px; color: var(--text-muted); }

        /* Interactive Native Accordions */
        details {
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 12px;
            margin-bottom: 20px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.02);
            transition: all 0.3s;
        }
        
        details:hover { border-color: var(--accent); box-shadow: 0 6px 12px rgba(0,0,0,0.05); }

        summary {
            padding: 20px;
            cursor: pointer;
            list-style: none;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 600;
        }
        summary::-webkit-details-marker { display: none; }
        
        .job-meta { display: flex; flex-direction: column; }
        .job-title { font-size: 1.2em; color: var(--text-main); }
        .job-date { font-size: 0.9em; color: var(--text-muted); font-weight: 400; margin-top: 4px; }
        
        /* The plus/minus icon */
        summary::after {
            content: '+';
            font-size: 1.5em;
            color: var(--accent);
            background: var(--bg-color);
            width: 32px;
            height: 32px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.3s;
        }
        details[open] summary::after { content: '−'; transform: rotate(180deg); }

        .details-content { padding: 0 20px 20px 20px; color: var(--text-muted); border-top: 1px solid var(--border); margin-top: 10px; padding-top: 15px; }
        .details-content ul { padding-left: 20px; margin-top: 10px; }
        .details-content li { margin-bottom: 8px; }
        .details-content strong { color: var(--text-main); }

        /* Responsive Design */
        @media (max-width: 900px) {
            .dashboard { grid-template-columns: 1fr; margin-top: 80px; }
            .sidebar { position: relative; top: 0; }
        }

        /* Print Styles - Forces everything open */
        @media print {
            body { background: #fff; color: #000; display: block; }
            .theme-switch-wrapper { display: none; }
            .dashboard { display: block; margin: 0; padding: 0; }
            .profile-card { box-shadow: none; border: none; padding: 0; margin-bottom: 30px; }
            details { border: none; box-shadow: none; margin-bottom: 15px; page-break-inside: avoid; }
            details[open] summary::after, summary::after { display: none; }
            .details-content { display: block !important; border-top: none; padding: 0; margin-top: 0; }
            summary { padding: 0 0 5px 0; border-bottom: 2px solid #ccc; margin-bottom: 10px; pointer-events: none; }
            .job-date { text-align: right; }
        }
    </style>
</head>
<body>

    <div class="theme-switch-wrapper">
        <label class="theme-switch-label" for="theme-switch">
            <input type="checkbox" id="theme-switch" class="theme-switch">
            🌓 Toggle Dark Mode
        </label>
    </div>

    <div class="dashboard">
        
        <div class="sidebar">
            <div class="profile-card">
                <h1>Claudio Giordani</h1>
                <div class="title">Chief Marketing Officer</div>
                
                <ul class="contact-list">
                    <li>📍 Milan, IT</li>
                    <li>📧 giordaniclaud@gmail.com</li>
                    <li>📱 +39 3394249482</li>
                    <li>🔗 <a href="https://www.linkedin.com/in/claudiogiordani/" target="_blank">LinkedIn Profile</a></li>
                </ul>

                <div class="skills-section">
                    <h3>Core Expertise</h3>
                    <div class="skill-tags">
                        <span class="tag">Go-to-Market Strategy</span>
                        <span class="tag">Digital Marketing</span>
                        <span class="tag">Global Team Leadership</span>
                        <span class="tag">Revenue Growth</span>
                        <span class="tag">Brand Equity</span>
                    </div>
                </div>

                <div class="skills-section" style="margin-top: 20px;">
                    <h3>Languages</h3>
                    <div class="skill-tags">
                        <span class="tag">Italian (Native)</span>
                        <span class="tag">English (Fluent)</span>
                        <span class="tag">Spanish (Proficient)</span>
                        <span class="tag">Portuguese (Advanced)</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="main-content">
            
            <h2>Executive Profile</h2>
            <p class="intro-text">Proven go-to-market leader in transforming marketing strategies into substantial revenue growth. With 18 years of experience driving adoption, revenue, and shareholder value at publicly traded companies and tech/SaaS scale-ups, I have a track record of overachieving targets and acting as a strategic partner to sales leadership. My expertise spans international marketing, product, brand & channel marketing, and advanced digital marketing. I am a creative and adaptable manager with strong leadership experience, inspiring diverse, distributed global teams through a structured, data-driven management style.</p>

            <h2>Professional Experience</h2>

            <details>
                <summary>
                    <div class="job-meta">
                        <span class="job-title">CMO, LianeCare</span>
                        <span class="job-date">09/2024 - Present | Milan, IT</span>
                    </div>
                </summary>
                <div class="details-content">
                    <p>Owner of marketing strategies driving brand visibility, user engagement, and market leadership in the corporate welfare sector. Focused on innovation and measurable outcomes, I lead initiatives that balance scalable growth with long-term brand equity.</p>
                    <ul>
                        <li><strong>Strategic Growth:</strong> Spearheaded the go-to-market strategy for the corporate welfare sector, balancing scalable user acquisition with long-term brand equity.</li>
                        <li><strong>Team Leadership:</strong> Built and currently mentor a high-performing team of 5, establishing a culture of "measurable outcomes" and fostering alignment between product and sales departments.</li>
                        <li><strong>Brand Authority:</strong> Elevated LianeCare's presence through targeted campaigns that position the company as the industry leader in well-being, directly resulting in increased organic traffic and improved brand favorability metrics.</li>
                        <li><strong>Operational Efficiency:</strong> Optimized marketing operations to achieve high ROI on cost-effective campaigns, boosting user loyalty while maintaining sustainable growth.</li>
                    </ul>
                </div>
            </details>

            <details>
                <summary>
                    <div class="job-meta">
                        <span class="job-title">Head of Marketing / Senior Marketing Leadership, BetterUp</span>
                        <span class="job-date">02/2022 - 12/2023 | San Francisco, USA</span>
                    </div>
                </summary>
                <div class="details-content">
                    <p>Owner of the international marketing strategy and execution for BetterUp, leading the go-to-market plan and marketing function for global expansion. Balanced growth across B2C and B2B markets while bringing BetterUp's product and message to market, fostering brand equity and growth.</p>
                    <ul>
                        <li><strong>Market expansion:</strong> Developed and executed the international GTM strategy, ensuring growth objectives were consistently met and a cohesive voice across a multi-cultural environment.</li>
                        <li><strong>Team management:</strong> Coordinated and mentored a distributed workforce to maintain agility and strategic alignment.</li>
                        <li><strong>Demand generation:</strong> Built a pipeline growth strategy, executing region-wide and country-specific campaigns to maximize impact.</li>
                        <li><strong>Operational excellence:</strong> Optimized marketing processes, including web presence, regional influencers, SEO, nurture campaigns, and marketing technology and automation systems.</li>
                        <li><strong>KPI Achievement:</strong> Consistently exceeded pipeline goals by 155% and brand awareness targets by 150% through rigorous benchmarking against competitors. Managed an 8-figure budget.</li>
                    </ul>
                </div>
            </details>

            <details>
                <summary>
                    <div class="job-meta">
                        <span class="job-title">Head of International Marketing - Google Assistant, Google</span>
                        <span class="job-date">10/2017 - 01/2022 | San Francisco, USA</span>
                    </div>
                </summary>
                <div class="details-content">
                    <p>Led the marketing efforts for internationalizing the Google Assistant in the fastest global expansion of a product in Google's history - Managed the product marketing strategy and the operations for the launch of a customized Google Assistant in +130 markets and +40 new languages to drive awareness, adoption and growth across users globally.</p>
                    <ul>
                        <li><strong>Career progression:</strong> Promoted to design and oversee all Google Assistant initiatives to support and enhance Diversity, Equity and Inclusion (dual role). Built and led the internationalization team (35 distributed people).</li>
                        <li><strong>Campaign Execution:</strong> Orchestrated +50 complex, multi-channel global campaigns that increased brand favorability and awareness in key international markets to grow an engaged user base. Designed processes, communication and product development strategies to increase market fit.</li>
                        <li><strong>KPI Achievement:</strong> Global DAUs grew 100x (to achieve 1B active users) and non-US markets grew to contribute from 0% to 70% of user base.</li>
                    </ul>
                </div>
            </details>

            <details>
                <summary>
                    <div class="job-meta">
                        <span class="job-title">Board member and Marketing Advisor, Userbot</span>
                        <span class="job-date">06/2021 - Present | Milan, IT</span>
                    </div>
                </summary>
                <div class="details-content">
                    <ul>
                        <li>Advising the founder on Series A fundraising positioning and B2B product-market fit.</li>
                    </ul>
                </div>
            </details>

            <details>
                <summary>
                    <div class="job-meta">
                        <span class="job-title">Lecturer of Marketing, John Cabot University and AUR</span>
                        <span class="job-date">01/2024 - 12/2024 | Rome, IT</span>
                    </div>
                </summary>
                <div class="details-content">
                    <ul>
                        <li>Teaching marketing principles, sharing real-world insights from 18 years in top-tier tech companies.</li>
                    </ul>
                </div>
            </details>

            <h2 style="margin-top: 40px;">Education & Credentials</h2>
            <details>
                <summary>
                    <div class="job-meta">
                        <span class="job-title">Academic History</span>
                    </div>
                </summary>
                <div class="details-content">
                    <ul>
                        <li><strong>Executive Program</strong>, Singularity University | Santa Clara, USA (2017)</li>
                        <li><strong>Marketing Academy Post-Grad</strong>, The Wharton School - Univ. of Pennsylvania | Philadelphia, USA (2014)</li>
                        <li><strong>Master of Science in International Markets and New Technologies (CLEMIT)</strong>, Università Commerciale Luigi Bocconi | Milan, IT (2008) - Full grades</li>
                        <li><strong>Bachelor of Science in International Economics and Management</strong>, Università Commerciale Luigi Bocconi | Milan, IT (2005) - Full grades</li>
                    </ul>
                </div>
            </details>
            
            <details>
                <summary>
                    <div class="job-meta">
                        <span class="job-title">Certifications</span>
                    </div>
                </summary>
                <div class="details-content">
                    <ul>
                        <li><strong>Google Ads:</strong> Fundamentals, Search Advertising, Video Advertising, Mobile Advertising, Display Advertising, Shopping Advertising</li>
                    </ul>
                </div>
            </details>

        </div>
    </div>

    <script>
        const toggleSwitch = document.querySelector('#theme-switch');
        
        // Listen for the toggle switch
        toggleSwitch.addEventListener('change', function(e) {
            if (e.target.checked) {
                document.documentElement.setAttribute('data-theme', 'dark');
            } else {
                document.documentElement.setAttribute('data-theme', 'light');
            }
        });

        // Small script to ensure all accordions are open if someone hits Ctrl+P to print
        window.addEventListener('beforeprint', () => {
            document.querySelectorAll('details').forEach(detail => detail.setAttribute('open', 'true'));
        });
    </script>
</body>
</html>
