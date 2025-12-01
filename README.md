# KVK23.github.io
from IPython.display import HTML

html_content = '''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Academic Portfolio - Services & Projects</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; background-color: #f4f4f4; color: #333; }
        header { background-color: #007bff; color: white; padding: 20px; text-align: center; }
        .hero { background-image: url('https://via.placeholder.com/1200x400?text=Your+Portfolio+Hero+Image'); background-size: cover; padding: 100px 20px; text-align: center; color: white; }
        .section { padding: 40px 20px; max-width: 1200px; margin: 0 auto; }
        .services { display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; }
        .service { background: white; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); padding: 20px; width: 300px; text-align: center; }
        .service img { width: 100%; height: 150px; object-fit: cover; border-radius: 8px; }
        .price { font-size: 24px; color: #007bff; margin: 10px 0; }
        button { background-color: #28a745; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; }
        button:hover { background-color: #218838; }
        footer { background-color: #333; color: white; text-align: center; padding: 20px; }
        form { max-width: 400px; margin: 0 auto; }
        input, textarea { width: 100%; padding: 10px; margin: 10px 0; border: 1px solid #ccc; border-radius: 5px; }
    </style>
</head>
<body>
    <header>
        <h1>Your Name's Academic Portfolio</h1>
        <p>Freelancing & Electronics Project Expert</p>
    </header>

    <section class="hero">
        <h2>Welcome to My Portfolio</h2>
        <p>Explore my services in freelancing and electronics projects. Hire me for your next project!</p>
    </section>

    <section class="section" id="about">
        <h2>About Me</h2>
        <p>I'm a passionate freelancer and electronics enthusiast with a background in [Your Field, e.g., Computer Science]. I specialize in web development, writing, circuit design, and prototyping. Let's build something amazing together!</p>
        <img src="https://via.placeholder.com/300x200?text=Your+Photo" alt="Your Photo" style="display: block; margin: 20px auto; border-radius: 50%;">
    </section>

    <section class="section" id="services">
        <h2>Services</h2>
        <div class="services">
            <div class="service">
                <img src="https://via.placeholder.com/300x200?text=Freelancing+Service" alt="Freelancing">
                <h3>Freelancing (Web Dev & Writing)</h3>
                <p>Custom web development, content writing, or general freelancing tasks. Perfect for startups and individuals.</p>
                <div class="price">$50 - $200</div>
                <button onclick="payNow('Freelancing Service', 5000)">Hire Now</button> <!-- Amount in paisa (e.g., 5000 = $50) -->
            </div>
            <div class="service">
                <img src="https://via.placeholder.com/300x200?text=Electronics+Project" alt="Electronics">
                <h3>Electronics Project Work</h3>
                <p>Circuit design, prototyping, IoT projects, or custom electronics solutions. From idea to working prototype.</p>
                <div class="price">$100 - $500</div>
                <button onclick="payNow('Electronics Project', 10000)">Order Now</button> <!-- Amount in paisa (e.g., 10000 = $100) -->
            </div>
        </div>
    </section>

    <section class="section" id="contact">
        <h2>Contact Me</h2>
        <form action="mailto:your-email@example.com" method="post" enctype="text/plain">
            <input type="text" name="name" placeholder="Your Name" required>
            <input type="email" name="email" placeholder="Your Email" required>
            <textarea name="message" placeholder="Your Message" rows="5" required></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <footer>
        <p>&copy; 2023 Your Name. All rights reserved. | <a href="https://razorpay.com" style="color: white;">Payments via Razorpay</a></p>
    </footer>

    <!-- Razorpay Integration Script -->
    <script src="https://checkout.razorpay.com/v1/checkout.js"></script>
    <script>
        function payNow(serviceName, amount) {
            var options = {
                "key": "YOUR_RAZORPAY_KEY_ID", //AReplace with your Razorpay Key ID
                "amount": amount, // Amount in paisa (e.g., 5000 = ₹50)
                "currency": "INR",
                "name": "Your Name's Portfolio",
                "description": serviceName,
                "image": "https://via.placeholder.com/100x100?text=Logo", // Optional logo
                "handler": function (response) {
                    alert("Payment successful! Payment ID: " + response.razorpay_payment_id);
                    // Here, you can send the payment details to your server for processing
                },
                "prefill": {
                    "name": "",
                    "email": "",
                    "contact": ""
                },
                "notes": {
                    "address": "Service: " + serviceName
                },
                "theme": {
                    "color": "#007bff"
                }
            };
            var rzp = new Razorpay(options);
            rzp.open();
        }
    </script>
</body>
</html>
'''

HTML(html_content)
