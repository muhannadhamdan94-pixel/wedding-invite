<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Muhannad & Waad Wedding</title>
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root { 
            --accent: #A89ACD;  /* Digital Lavender */
            --bg: #F1F0E4;      /* Cloud Dancer */
            --text: #3E3F29;    /* Deep Forest */
            --sage: #8F9C84;    /* Sage Eucalyptus */
            --gold: #D4AF37;    /* Subtle Gold */
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body { 
            font-family: 'Quicksand', sans-serif; 
            background: var(--bg); 
            color: var(--text);
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 15px;
            overflow-x: hidden;
        }

        .main-container {
            width: 100%;
            max-width: 900px;
            display: flex;
            justify-content: center;
        }

        /* Responsive Postcard View */
        .postcard {
            background: white;
            width: 100%;
            aspect-ratio: 9 / 6; /* Classic Postcard Ratio for Desktop */
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            border-radius: 4px;
            box-shadow: 0 15px 45px rgba(62, 63, 41, 0.08);
            padding: 40px;
            position: relative;
            border: 1px solid rgba(212, 175, 55, 0.2);
            transition: all 0.3s ease;
        }

        .postcard::before {
            content: "";
            position: absolute;
            top: 15px; right: 15px; bottom: 15px; left: 15px;
            border: 1px solid var(--gold);
            pointer-events: none;
            opacity: 0.4;
        }

        .postcard h1 {
            font-size: clamp(1.8rem, 6vw, 3.5rem);
            font-weight: 500;
            letter-spacing: 4px;
            margin-bottom: 10px;
            text-transform: uppercase;
        }

        .postcard .intro-text {
            color: var(--sage);
            font-size: clamp(1rem, 3vw, 1.2rem);
            margin-bottom: 20px;
            letter-spacing: 2px;
            font-weight: 400;
        }

        .postcard .venue-line {
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.75rem;
            margin-bottom: 35px;
            color: var(--text);
            font-weight: 600;
            line-height: 1.6;
        }

        /* RSVP Card (Hidden initially) */
        .rsvp-card { 
            background: white; 
            padding: 40px 25px; 
            border-radius: 12px; 
            box-shadow: 0 10px 40px rgba(143, 156, 132, 0.15); 
            width: 100%; 
            max-width: 450px; 
            display: none; 
            animation: fadeIn 0.5s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h2 { 
            text-align: center; 
            color: var(--accent); 
            margin-bottom: 5px; 
            font-weight: 600;
            letter-spacing: 4px;
            text-transform: uppercase;
            font-size: 1.6rem;
        }

        .loc-btn { 
            display: block; 
            text-align: center; 
            margin-bottom: 25px; 
            color: var(--sage); 
            text-decoration: none; 
            font-size: 0.7rem; 
            letter-spacing: 1px;
            font-weight: 700;
            text-transform: uppercase;
        }

        .form-group { margin-bottom: 18px; }
        
        label { 
            display: block; 
            font-size: 0.65rem; 
            text-transform: uppercase; 
            margin-bottom: 6px; 
            letter-spacing: 1.2px;
            font-weight: 700;
            color: var(--sage);
        }

        input, select { 
            width: 100%; 
            padding: 12px; 
            border: 1px solid #EAECE8; 
            border-radius: 8px; 
            font-size: 1rem;
            color: var(--text);
            font-family: 'Quicksand', sans-serif;
            background-color: #FAFAFA;
            -webkit-appearance: none; /* Fix for iOS styling */
        }

        .btn-main { 
            width: 100%; 
            background: var(--accent); 
            color: white; 
            padding: 16px; 
            border: none; 
            border-radius: 50px; 
            cursor: pointer; 
            text-transform: uppercase; 
            letter-spacing: 3px;
            font-size: 0.9rem;
            font-weight: 700;
            font-family: 'Quicksand', sans-serif;
            transition: transform 0.2s ease, background 0.2s ease;
            box-shadow: 0 4px 12px rgba(168, 154, 205, 0.3);
            margin-top: 10px;
        }

        .btn-main:active { transform: scale(0.98); }

        #success { display: none; text-align: center; padding: 40px 10px; }

        /* Mobile Adjustments */
        @media (max-width: 768px) {
            .postcard { 
                aspect-ratio: auto; /* Remove fixed ratio on mobile */
                padding: 50px 25px;
                min-height: 400px;
            }
            .postcard h1 { letter-spacing: 2px; }
            .main-container { padding: 10px; }
        }
    </style>
</head>
<body>

    <div class="main-container">
        <div id="landing" class="postcard">
            <p class="intro-text">The Celebration of</p>
            <h1>Muhannad & Waad</h1>
            <div class="venue-line">The St. Regis • New Capital, Cairo</div>
            <button class="btn-main" style="max-width: 220px;" onclick="openRSVP()">RSVP</button>
        </div>

        <div id="rsvp-ui" class="rsvp-card">
            <div id="form-content">
                <h2>RSVP</h2>
                <a href="https://maps.google.com" class="loc-btn" target="_blank">📍 View Venue Location</a>
                
                <form id="rsvp-form" action="https://script.google.com/macros/s/AKfycbycWn0jrrzNT71usnDlFJYipK_epfnRtUg4NfKJ5Sspc-nSiIGyNc07vujX9YcuGNho/exec">
                    <div class="form-group">
                        <label>Full Name</label>
                        <input type="text" name="name" required placeholder="Enter your name">
                    </div>

                    <div class="form-group">
                        <label>Phone Number</label>
                        <input type="tel" name="phone" required placeholder="+20 000 000 0000">
                    </div>

                    <div class="form-group">
                        <label>Will you attend?</label>
                        <select name="attending" required>
                            <option value="" disabled selected>Please select</option>
                            <option value="yes">Joyfully Accept</option>
                            <option value="no">Regretfully Decline</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label>Likelihood of Attending</label>
                        <select name="likelihood" required>
                            <option value="" disabled selected>Select likelihood</option>
                            <option value="100%">100% - Definitely</option>
                            <option value="75%">75% - Likely</option>
                            <option value="50%">50% - Planning to</option>
                        </select>
                    </div>

                    <button type="submit" class="btn-main" id="submit-btn">Send RSVP</button>
                </form>
            </div>

            <div id="success">
                <h3 style="color: var(--accent); font-size: 1.8rem; margin-bottom: 10px;">Thank You</h3>
                <p>Your response has been saved successfully.</p>
            </div>
        </div>
    </div>

    <script>
        function openRSVP() {
            document.getElementById('landing').style.display = 'none';
            document.getElementById('rsvp-ui').style.display = 'block';
            window.scrollTo(0, 0);
        }

        const form = document.getElementById('rsvp-form');
        const sBtn = document.getElementById('submit-btn');

        form.addEventListener('submit', e => {
            e.preventDefault();
            sBtn.disabled = true;
            sBtn.innerText = "Sending...";

            fetch(form.action, {
                method: 'POST',
                body: new FormData(form),
                mode: 'no-cors' 
            })
            .then(() => {
                document.getElementById('form-content').style.display = 'none';
                document.getElementById('success').style.display = 'block';
            })
            .catch(() => {
                alert("Something went wrong. Please try again.");
                sBtn.disabled = false;
                sBtn.innerText = "Send RSVP";
            });
        });
    </script>
</body>
</html>
