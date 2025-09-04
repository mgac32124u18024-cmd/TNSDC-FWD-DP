 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Climate Change Portfolio</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Climate Change Awareness</h1>
        <p>Explore data, trends, and what you can do to help.</p>
    </header>
    <section class="info">
        <h2>What is Climate Change?</h2>
        <p>
            Climate change refers to the long-term shift in global or regional climate patterns, often driven by human activities such as burning fossil fuels and deforestation.
        </p>
        <ul>
            <li>Rising global temperatures</li>
            <li>Increasing frequency of extreme weather events</li>
            <li>Melting polar ice and rising sea levels</li>
        </ul>
    </section>
    <section class="stats">
        <h2>Global Temperature Rise: 1880–2020</h2>
        <canvas id="tempChart" width="600" height="300"></canvas>
    </section>
    <footer>
        <p>&copy; 2025 Climate Change Portfolio. Data source: NASA GISS.</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
[03/09, 8:10 pm] prasanth Clg Friend: /* style.css */
body {
    font-family: Arial, sans-serif;
    background: #f5f6fa;
    margin: 0;
}

header {
    background: #2d98da;
    color: #fff;
    padding: 40px 0 10px 0;
    text-align: center;
}

.info {
    margin: 30px auto 0 auto;
    max-width: 700px;
    background: #fff;
    padding: 30px 40px;
    border-radius: 8px;
    box-shadow: 0 5px 15px rgba(80,80,80,0.07);
}

.stats {
    text-align: center;
    margin: 40px auto 0 auto;
    background: #eaf0fb;
    padding: 25px 10px 30px 10px;
    border-radius: 8px;
    max-width: 700px;
    box-shadow: 0 2px 10px rgba(80,80,80,0.05);
}

footer {
    margin-top: 40px;
    text-align: center;
    color: #aaa;
    background: #222f3e;
    padding: 15px 0;
    font-size: 14px;
}
// script.js
const canvas = document.getElementById('tempChart');
const ctx = canvas.getContext('2d');

// Example temperature anomaly data: [year, anomaly in °C]
const data = [
    [1880, -0.2], [1890, -0.1], [1900, 0.0], [1910, -0.1],
    [1920, 0.0], [1930, 0.1], [1940, 0.05], [1950, 0.0],
    [1960, 0.02], [1970, 0.1], [1980, 0.2], [1990, 0.32],
    [2000, 0.40], [2010, 0.7], [2020, 0.98]
];

// Chart dimensions
const width = canvas.width;
const height = canvas.height;
const padding = 50;

// Find min/max for scaling
const years = data.map(x => x);
const temps = data.map(x => x[1]);
const minYear = Math.min(...years);
const maxYear = Math.max(...years);
const minTemp = Math.min(...temps);
const maxTemp = Math.max(...temps);

// Draw axes
ctx.strokeStyle = '#181818';
ctx.beginPath();
ctx.moveTo(padding, padding);
ctx.lineTo(padding, height - padding);
ctx.lineTo(width - padding, height - padding);
ctx.stroke();

// Plot data
ctx.strokeStyle = '#e17055';
ctx.lineWidth = 3;
ctx.beginPath();
data.forEach(([year, anomaly], idx) => {
    // Scale points
    const x = padding + ((year - minYear) / (maxYear - minYear)) * (width - 2 * padding);
    const y = height - padding - ((anomaly - minTemp) / (maxTemp - minTemp)) * (height - 2 * padding);
    if (idx === 0) ctx.moveTo(x, y);
    else ctx.lineTo(x, y);
});
ctx.stroke();

// Add labels
ctx.fillStyle = "#181818";
ctx.font = "14px Arial";
ctx.fillText(`${minYear}`, padding, height - padding + 20);
ctx.fillText(`${maxYear}`, width - padding - 35, height - padding + 20);
ctx.fillText(`${minTemp}°C`, padding - 45, height - padding + 5);
ctx.fillText(`${maxTemp}°C`, padding - 45, padding + 5);
[03/0 <!-- About Me Section -->
<section class="about-me">
    <h2>About Me</h2>
    <p>
        Hi! I'm [jagathees k], a passionate web developer and emerging environmental advocate. I use technology to spread awareness about issues like climate change and to create interactive experiences that inspire positive change.
    </p>
    <ul class="about-list">
        <li><strong>Focus:</strong> Frontend Development, Data Visualization</li>
        <li><strong>Languages:</strong> HTML, CSS, JavaScript</li>
        <li><strong>Portfolio:</strong> <a href="https://your-portfolio-link.com" target="_blank">your-portfolio-link.com</a></li>
    </ul>
</section>

<!-- Contact Details Section -->
<section class="contact-details">
    <h2>Contact</h2>
    <p>Feel free to reach out for collaborations, questions, or project discussions!</p>
    <ul>
        <li><strong>Email:</strong> <a href="mailto:your.email@example.com">your.email@example.com</a></li>
        <li><strong>LinkedIn:</strong> <a href="https://linkedin.com/in/yourprofile" target="_blank">linkedin.com/in/yourprofile</a></li>
        <li><strong>GitHub:</strong> <a href="https://github.com/yourusername" target="_blank">github.com/yourusername</a></li>
    </ul>
    <!-- Example contact form (optional) -->
    <form class="contact-form" autocomplete="off">
        <input type="text" name="name" placeholder="Your Name" required>
        <input type="email" name="email" placeholder="Your Email" required>
        <textarea name="message" placeholder="Write your message" required></textarea>
        <button type="submit">Send Message</button>
    </form>
</section>
 .about-me, .contact-details {
    max-width: 700px;
    background: #fff;
    padding: 30px 40px;
    margin: 40px auto 0 auto;
    border-radius: 8px;
    box-shadow: 0 5px 18px rgba(120,120,120,0.06);
}

.about-me h2, .contact-details h2 {
    color: #2d98da;
    margin-bottom: 15px;
}

.about-list {
    margin-top: 16px;
    list-style-type: square;
    padding-left: 20px;
}

.contact-details ul {
    list-style: none;
    padding: 0;
    margin: 16px 0 24px 0;
}

.contact-details li {
    margin-bottom: 10px;
}

.contact-form {
    display: flex;
    flex-direction: column;
    gap: 13px;
}

.contact-form input,
.contact-form textarea {
    padding: 10px;
    border-radius: 5px;
    border: 1px solid #cfd1d4;
    font-size: 1em;
}

.contact-form button {
    background: #2d98da;
    color: #fff;
    border: none;
    padding: 12px 0;
    border-radius: 5px;
    font-size: 1em;
    cursor: pointer;
    transition: background .2s;
}

.contact-form button:hover {
    background: #4578a7;
}
