<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JMATHCODE - সৃজনশীল ডিজাইন ও প্রোগ্রামিং</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #6C63FF;
            --secondary-color: #4D44DB;
            --accent-color: #FF6584;
            --dark-color: #2D3748;
            --light-color: #F7FAFC;
            --gradient: linear-gradient(135deg, #6C63FF 0%, #FF6584 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f9f9f9;
            color: var(--dark-color);
            line-height: 1.6;
        }

        /* হেডার স্টাইল */
        header {
            background: var(--gradient);
            color: white;
            padding: 1rem 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
        }

        .logo i {
            margin-right: 10px;
            color: var(--accent-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 0.5rem 0;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--accent-color);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            cursor: pointer;
        }

        /* হিরো সেকশন */
        .hero {
            background: var(--gradient);
            color: white;
            padding: 5rem 2rem;
            text-align: center;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 0.8rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        /* কন্টেন্ট সেকশন */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--dark-color);
            display: inline-block;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--gradient);
            border-radius: 2px;
        }

        /* ডিজাইন গ্যালারি */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .gallery-item {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .gallery-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .gallery-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .gallery-info {
            padding: 1.5rem;
        }

        .gallery-info h3 {
            margin-bottom: 0.5rem;
            color: var(--dark-color);
        }

        .gallery-info p {
            color: #666;
            margin-bottom: 1rem;
        }

        /* ভিডিও সেকশন */
        .video-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .video-item {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 aspect ratio */
            height: 0;
            overflow: hidden;
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        .video-info {
            padding: 1.5rem;
        }

        /* এডিট মোড */
        .edit-mode {
            background-color: #f0f0f0;
            padding: 2rem;
            border-radius: 10px;
            margin-top: 3rem;
            display: none;
        }

        .edit-mode h3 {
            margin-bottom: 1rem;
            color: var(--dark-color);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--dark-color);
        }

        .form-control {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border 0.3s ease;
        }

        .form-control:focus {
            border-color: var(--primary-color);
            outline: none;
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* ফুটার */
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 3rem 0;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: left;
        }

        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            position: relative;
            display: inline-block;
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 50px;
            height: 3px;
            background: var(--gradient);
        }

        .footer-column p {
            margin-bottom: 1rem;
            opacity: 0.8;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background-color: var(--accent-color);
            transform: translateY(-3px);
        }

        .copyright {
            margin-top: 3rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            opacity: 0.7;
        }

        /* রেস্পন্সিভ ডিজাইন */
        @media (max-width: 768px) {
            .navbar {
                padding: 1rem;
            }

            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background-color: var(--primary-color);
                flex-direction: column;
                align-items: center;
                justify-content: center;
                transition: all 0.5s ease;
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links li {
                margin: 1rem 0;
            }

            .hamburger {
                display: block;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .section-title h2 {
                font-size: 2rem;
            }

            .gallery {
                grid-template-columns: 1fr;
            }

            .video-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- হেডার সেকশন -->
    <header>
        <nav class="navbar">
            <div class="logo">
                <i class="fas fa-code"></i>
                <span>JMATHCODE</span>
            </div>
            <ul class="nav-links">
                <li><a href="#home">হোম</a></li>
                <li><a href="#designs">ডিজাইন</a></li>
                <li><a href="#videos">ভিডিও</a></li>
                <li><a href="#about">আমার সম্পর্কে</a></li>
                <li><a href="#contact">যোগাযোগ</a></li>
            </ul>
            <div class="hamburger">
                <i class="fas fa-bars"></i>
            </div>
        </nav>
    </header>

    <!-- হিরো সেকশন -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>আমার সৃজনশীল ডিজাইন ও প্রোগ্রামিং জার্নি</h1>
            <p>এখানে আপনি আমার তৈরি করা বিভিন্ন ডিজাইন, প্রজেক্ট এবং ভিডিও টিউটোরিয়াল দেখতে পারবেন</p>
            <a href="#designs" class="btn">আমার ডিজাইন দেখুন</a>
            <button id="editToggleBtn" class="btn" style="margin-left: 10px; background: var(--dark-color);">এডিট মোড</button>
        </div>
    </section>

    <!-- ডিজাইন গ্যালারি সেকশন -->
    <section class="container" id="designs">
        <div class="section-title">
            <h2>আমার ডিজাইনসমূহ</h2>
        </div>
        <div class="gallery" id="designGallery">
            <!-- ডিজাইন আইটেমগুলি এখানে যোগ হবে -->
            <div class="gallery-item">
                <img src="https://via.placeholder.com/600x400?text=Design+1" alt="Design 1" class="gallery-img">
                <div class="gallery-info">
                    <h3>ওয়েব ডিজাইন ১</h3>
                    <p>এটি একটি আধুনিক ওয়েবসাইট ডিজাইন যা HTML, CSS এবং JavaScript ব্যবহার করে তৈরি করা হয়েছে।</p>
                    <a href="#" class="btn">বিস্তারিত দেখুন</a>
                </div>
            </div>
            <div class="gallery-item">
                <img src="https://via.placeholder.com/600x400?text=Design+2" alt="Design 2" class="gallery-img">
                <div class="gallery-info">
                    <h3>মোবাইল অ্যাপ ইন্টারফেস</h3>
                    <p>এটি একটি ইউজার ফ্রেন্ডলি মোবাইল অ্যাপ্লিকেশনের ইন্টারফেস ডিজাইন।</p>
                    <a href="#" class="btn">বিস্তারিত দেখুন</a>
                </div>
            </div>
            <div class="gallery-item">
                <img src="https://via.placeholder.com/600x400?text=Design+3" alt="Design 3" class="gallery-img">
                <div class="gallery-info">
                    <h3>লোগো ডিজাইন</h3>
                    <p>এটি একটি ইউনিক লোগো ডিজাইন যা ভেক্টর গ্রাফিক্স ব্যবহার করে তৈরি করা হয়েছে।</p>
                    <a href="#" class="btn">বিস্তারিত দেখুন</a>
                </div>
            </div>
        </div>

        <!-- এডিট মোড ফর্ম (ডিজাইন) -->
        <div class="edit-mode" id="designEditForm">
            <h3>নতুন ডিজাইন যোগ করুন</h3>
            <form id="addDesignForm">
                <div class="form-group">
                    <label for="designTitle">ডিজাইনের শিরোনাম</label>
                    <input type="text" id="designTitle" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="designImage">ইমেজ URL</label>
                    <input type="url" id="designImage" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="designDesc">বিবরণ</label>
                    <textarea id="designDesc" class="form-control" required></textarea>
                </div>
                <button type="submit" class="btn">যোগ করুন</button>
            </form>
        </div>
    </section>

    <!-- ভিডিও সেকশন -->
    <section class="container" id="videos">
        <div class="section-title">
            <h2>আমার ভিডিওসমূহ</h2>
        </div>
        <div class="video-container" id="videoGallery">
            <!-- ভিডিও আইটেমগুলি এখানে যোগ হবে -->
            <div class="video-item">
                <div class="video-wrapper">
                    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" allowfullscreen></iframe>
                </div>
                <div class="video-info">
                    <h3>HTML & CSS টিউটোরিয়াল</h3>
                    <p>এই ভিডিওতে আমি HTML এবং CSS এর বেসিক কনসেপ্টগুলি আলোচনা করেছি।</p>
                </div>
            </div>
            <div class="video-item">
                <div class="video-wrapper">
                    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" allowfullscreen></iframe>
                </div>
                <div class="video-info">
                    <h3>জাভাস্ক্রিপ্ট প্রজেক্ট</h3>
                    <p>এই ভিডিওতে আমি একটি ইন্টারেক্টিভ জাভাস্ক্রিপ্ট প্রজেক্ট তৈরি করেছি।</p>
                </div>
            </div>
        </div>

        <!-- এডিট মোড ফর্ম (ভিডিও) -->
        <div class="edit-mode" id="videoEditForm">
            <h3>নতুন ভিডিও যোগ করুন</h3>
            <form id="addVideoForm">
                <div class="form-group">
                    <label for="videoTitle">ভিডিও শিরোনাম</label>
                    <input type="text" id="videoTitle" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="videoUrl">ইউটিউব ভিডিও URL</label>
                    <input type="url" id="videoUrl" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="videoDesc">বিবরণ</label>
                    <textarea id="videoDesc" class="form-control" required></textarea>
                </div>
                <button type="submit" class="btn">যোগ করুন</button>
            </form>
        </div>
    </section>

    <!-- আমার সম্পর্কে সেকশন -->
    <section class="container" id="about">
        <div class="section-title">
            <h2>আমার সম্পর্কে</h2>
        </div>
        <div class="about-content" style="background: white; padding: 2rem; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.1);">
            <div style="display: flex; align-items: center; margin-bottom: 2rem;">
                <img src="https://via.placeholder.com/150" alt="My Photo" style="width: 150px; height: 150px; border-radius: 50%; object-fit: cover; margin-right: 2rem;">
                <div>
                    <h3 style="font-size: 1.8rem; margin-bottom: 0.5rem;">আমার নাম</h3>
                    <p style="color: var(--primary-color); font-weight: 600; margin-bottom: 1rem;">ওয়েব ডিজাইনার ও ডেভেলপার</p>
                    <p>আমি একজন প্যাশনেট ওয়েব ডিজাইনার এবং ডেভেলপার। আমি নতুন নতুন ডিজাইন তৈরি করতে এবং কোডিং করতে ভালোবাসি।</p>
                </div>
            </div>
            <div id="aboutText">
                <p>আমি প্রায় ৫ বছর ধরে ওয়েব ডিজাইন এবং ডেভেলপমেন্টের সাথে জড়িত। আমি HTML, CSS, JavaScript, React এবং Node.js সহ বিভিন্ন প্রযুক্তিতে কাজ করেছি। আমার লক্ষ্য হলো সুন্দর এবং ইউজার ফ্রেন্ডলি ইন্টারফেস ডিজাইন করা যা ব্যবহারকারীদের জন্য আনন্দদায়ক অভিজ্ঞতা তৈরি করে।</p>
                <p>আমি নিয়মিত নতুন নতুন প্রযুক্তি শিখতে এবং আমার দক্ষতা উন্নত করতে পছন্দ করি। আমি বিশ্বাস করি যে শেখার কোনো শেষ নেই এবং প্রতিদিনই আমরা নতুন কিছু শিখতে পারি।</p>
            </div>
        </div>

        <!-- এডিট মোড ফর্ম (আমার সম্পর্কে) -->
        <div class="edit-mode" id="aboutEditForm">
            <h3>আমার তথ্য আপডেট করুন</h3>
            <form id="updateAboutForm">
                <div class="form-group">
                    <label for="aboutName">আপনার নাম</label>
                    <input type="text" id="aboutName" class="form-control" value="আমার নাম" required>
                </div>
                <div class="form-group">
                    <label for="aboutTitle">পেশা/টাইটেল</label>
                    <input type="text" id="aboutTitle" class="form-control" value="ওয়েব ডিজাইনার ও ডেভেলপার" required>
                </div>
                <div class="form-group">
                    <label for="aboutImage">প্রোফাইল ইমেজ URL</label>
                    <input type="url" id="aboutImage" class="form-control" value="https://via.placeholder.com/150" required>
                </div>
                <div class="form-group">
                    <label for="aboutTextArea">আপনার সম্পর্কে</label>
                    <textarea id="aboutTextArea" class="form-control" required>আমি প্রায় ৫ বছর ধরে ওয়েব ডিজাইন এবং ডেভেলপমেন্টের সাথে জড়িত। আমি HTML, CSS, JavaScript, React এবং Node.js সহ বিভিন্ন প্রযুক্তিতে কাজ করেছি। আমার লক্ষ্য হলো সুন্দর এবং ইউজার ফ্রেন্ডলি ইন্টারফেস ডিজাইন করা যা ব্যবহারকারীদের জন্য আনন্দদায়ক অভিজ্ঞতা তৈরি করে।

আমি নিয়মিত নতুন নতুন প্রযুক্তি শিখতে এবং আমার দক্ষতা উন্নত করতে পছন্দ করি। আমি বিশ্বাস করি যে শেখার কোনো শেষ নেই এবং প্রতিদিনই আমরা নতুন কিছু শিখতে পারি।</textarea>
                </div>
                <button type="submit" class="btn">আপডেট করুন</button>
            </form>
        </div>
    </section>

    <!-- যোগাযোগ সেকশন -->
    <section class="container" id="contact">
        <div class="section-title">
            <h2>যোগাযোগ</h2>
        </div>
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem;">
            <div style="background: white; padding: 2rem; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.1);">
                <h3 style="margin-bottom: 1.5rem;">আমাকে মেসেজ পাঠান</h3>
                <form id="contactForm">
                    <div class="form-group">
                        <label for="contactName">আপনার নাম</label>
                        <input type="text" id="contactName" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label for="contactEmail">ইমেইল ঠিকানা</label>
                        <input type="email" id="contactEmail" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label for="contactMessage">মেসেজ</label>
                        <textarea id="contactMessage" class="form-control" required></textarea>
                    </div>
                    <button type="submit" class="btn">পাঠান</button>
                </form>
            </div>
            <div style="background: white; padding: 2rem; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.1);">
                <h3 style="margin-bottom: 1.5rem;">আমার সাথে যোগাযোগ</h3>
                <div style="margin-bottom: 1.5rem;">
                    <h4 style="margin-bottom: 0.5rem; color: var(--primary-color);"><i class="fas fa-envelope" style="margin-right: 10px;"></i>ইমেইল</h4>
                    <p>example@jmathcode.com</p>
                </div>
                <div style="margin-bottom: 1.5rem;">
                    <h4 style="margin-bottom: 0.5rem; color: var(--primary-color);"><i class="fas fa-phone" style="margin-right: 10px;"></i>ফোন</h4>
                    <p>+880 1XXX XXXXXX</p>
                </div>
                <div>
                    <h4 style="margin-bottom: 0.5rem; color: var(--primary-color);"><i class="fas fa-map-marker-alt" style="margin-right: 10px;"></i>ঠিকানা</h4>
                    <p>আপনার ঠিকানা, শহর, বাংলাদেশ</p>
                </div>
                <div class="social-links" style="margin-top: 2rem; justify-content: flex-start;">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
        </div>

        <!-- এডিট মোড ফর্ম (যোগাযোগ) -->
        <div class="edit-mode" id="contactEditForm">
            <h3>যোগাযোগ তথ্য আপডেট করুন</h3>
            <form id="updateContactForm">
                <div class="form-group">
                    <label for="contactEmailInput">ইমেইল</label>
                    <input type="email" id="contactEmailInput" class="form-control" value="example@jmathcode.com" required>
                </div>
                <div class="form-group">
                    <label for="contactPhoneInput">ফোন</label>
                    <input type="text" id="contactPhoneInput" class="form-control" value="+880 1XXX XXXXXX" required>
                </div>
                <div class="form-group">
                    <label for="contactAddressInput">ঠিকানা</label>
                    <textarea id="contactAddressInput" class="form-control" required>আপনার ঠিকানা, শহর, বাংলাদেশ</textarea>
                </div>
                <div class="form-group">
                    <label for="contactSocialInput">সোশ্যাল মিডিয়া লিংকস (কমা দ্বারা পৃথক করুন)</label>
                    <textarea id="contactSocialInput" class="form-control" required>Facebook, Twitter, Instagram, LinkedIn, YouTube</textarea>
                </div>
                <button type="submit" class="btn">আপডেট করুন</button>
            </form>
        </div>
    </section>

    <!-- ফুটার -->
    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h3>JMATHCODE</h3>
                <p>সৃজনশীল ডিজাইন এবং ইনোভেটিভ প্রোগ্রামিং সলিউশনের জন্য একটি প্ল্যাটফর্ম।</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                </div>
            </div>
            <div class="footer-column">
                <h3>লিংকস</h3>
                <p><a href="#home" style="color: white; text-decoration: none;">হোম</a></p>
                <p><a href="#designs" style="color: white; text-decoration: none;">ডিজাইন</a></p>
                <p><a href="#videos" style="color: white; text-decoration: none;">ভিডিও</a></p>
                <p><a href="#about" style="color: white; text-decoration: none;">আমার সম্পর্কে</a></p>
                <p><a href="#contact" style="color: white; text-decoration: none;">যোগাযোগ</a></p>
            </div>
            <div class="footer-column">
                <h3>সেবাসমূহ</h3>
                <p>ওয়েব ডিজাইন</p>
                <p>ওয়েব ডেভেলপমেন্ট</p>
                <p>গ্রাফিক ডিজাইন</p>
                <p>ভিডিও এডিটিং</p>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2023 JMATHCODE. সকল স্বত্ব সংরক্ষিত।</p>
        </div>
    </footer>

    <script>
        // হ্যামবার্গার মেনু টগল
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');

        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.innerHTML = navLinks.classList.contains('active') ? 
                '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
        });

        // এডিট মোড টগল
        const editToggleBtn = document.getElementById('editToggleBtn');
        const editForms = [
            document.getElementById('designEditForm'),
            document.getElementById('videoEditForm'),
            document.getElementById('aboutEditForm'),
            document.getElementById('contactEditForm')
        ];

        let editMode = false;

        editToggleBtn.addEventListener('click', () => {
            editMode = !editMode;
            editForms.forEach(form => {
                form.style.display = editMode ? 'block' : 'none';
            });
            editToggleBtn.textContent = editMode ? 'এডিট মোড বন্ধ করুন' : 'এডিট মোড';
            editToggleBtn.style.backgroundColor = editMode ? 'var(--accent-color)' : 'var(--dark-color)';
        });

        // ডিজাইন যোগ করার ফর্ম
        const addDesignForm = document.getElementById('addDesignForm');
        const designGallery = document.getElementById('designGallery');

        addDesignForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const title = document.getElementById('designTitle').value;
            const imageUrl = document.getElementById('designImage').value;
            const description = document.getElementById('designDesc').value;
            
            const newDesign = document.createElement('div');
            newDesign.className = 'gallery-item';
            newDesign.innerHTML = `
                <img src="${imageUrl}" alt="${title}" class="gallery-img">
                <div class="gallery-info">
                    <h3>${title}</h3>
                    <p>${description}</p>
                    <a href="#" class="btn">বিস্তারিত দেখুন</a>
                </div>
            `;
            
            designGallery.appendChild(newDesign);
            addDesignForm.reset();
            alert('ডিজাইন সফলভাবে যোগ করা হয়েছে!');
        });

        // ভিডিও যোগ করার ফর্ম
        const addVideoForm = document.getElementById('addVideoForm');
        const videoGallery = document.getElementById('videoGallery');

        addVideoForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const title = document.getElementById('videoTitle').value;
            const videoUrl = document.getElementById('videoUrl').value;
            const description = document.getElementById('videoDesc').value;
            
            // Extract YouTube video ID from URL
            let videoId = '';
            if (videoUrl.includes('youtube.com/watch?v=')) {
                videoId = videoUrl.split('v=')[1].split('&')[0];
            } else if (videoUrl.includes('youtu.be/')) {
                videoId = videoUrl.split('youtu.be/')[1].split('?')[0];
            }
            
            if (!videoId) {
                alert('দুঃখিত, ভিডিও URL টি সঠিক নয়। দয়া করে একটি বৈধ ইউটিউব ভিডিও URL প্রদান করুন।');
                return;
            }
            
            const newVideo = document.createElement('div');
            newVideo.className = 'video-item';
            newVideo.innerHTML = `
                <div class="video-wrapper">
                    <iframe src="https://www.youtube.com/embed/${videoId}" allowfullscreen></iframe>
                </div>
                <div class="video-info">
                    <h3>${title}</h3>
                    <p>${description}</p>
                </div>
            `;
            
            videoGallery.appendChild(newVideo);
            addVideoForm.reset();
            alert('ভিডিও সফলভাবে যোগ করা হয়েছে!');
        });

        // আমার সম্পর্কে আপডেট ফর্ম
        const updateAboutForm = document.getElementById('updateAboutForm');
        const aboutText = document.getElementById('aboutText');

        updateAboutForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const name = document.getElementById('aboutName').value;
            const title = document.getElementById('aboutTitle').value;
            const imageUrl = document.getElementById('aboutImage').value;
            const aboutContent = document.getElementById('aboutTextArea').value;
            
            // Update the about section
            document.querySelector('.about-content h3').textContent = name;
            document.querySelector('.about-content p:nth-of-type(1)').textContent = title;
            document.querySelector('.about-content img').src = imageUrl;
            
            // Update the about text
            aboutText.innerHTML = aboutContent.split('\n').map(para => `<p>${para}</p>`).join('');
            
            alert('আমার সম্পর্কে তথ্য সফলভাবে আপডেট করা হয়েছে!');
        });

        // যোগাযোগ তথ্য আপডেট ফর্ম
        const updateContactForm = document.getElementById('updateContactForm');

        updateContactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const email = document.getElementById('contactEmailInput').value;
            const phone = document.getElementById('contactPhoneInput').value;
            const address = document.getElementById('contactAddressInput').value;
            const socialLinks = document.getElementById('contactSocialInput').value.split(',');
            
            // Update contact information
            document.querySelector('#contact p:nth-of-type(1)').textContent = email;
            document.querySelector('#contact p:nth-of-type(2)').textContent = phone;
            document.querySelector('#contact p:nth-of-type(3)').textContent = address;
            
            // Update social links (simplified for demo)
            const socialIcons = ['facebook-f', 'twitter', 'instagram', 'linkedin-in', 'youtube'];
            const socialContainer = document.querySelector('#contact .social-links');
            socialContainer.innerHTML = '';
            
            socialLinks.forEach((link, index) => {
                if (index < socialIcons.length) {
                    const a = document.createElement('a');
                    a.href = '#';
                    a.innerHTML = `<i class="fab fa-${socialIcons[index]}"></i>`;
                    socialContainer.appendChild(a);
                }
            });
            
            alert('যোগাযোগ তথ্য সফলভাবে আপডেট করা হয়েছে!');
        });

        // যোগাযোগ ফর্ম সাবমিশন
        const contactForm = document.getElementById('contactForm');

        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const name = document.getElementById('contactName').value;
            const email = document.getElementById('contactEmail').value;
            const message = document.getElementById('contactMessage').value;
            
            // Here you would typically send the data to a server
            // For this demo, we'll just show an alert
            alert(`ধন্যবাদ ${name}! আপনার মেসেজটি সফলভাবে পাঠানো হয়েছে। আমি শীঘ্রই আপনার সাথে যোগাযোগ করবো।`);
            contactForm.reset();
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 70,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    if (navLinks.classList.contains('active')) {
                        navLinks.classList.remove('active');
                        hamburger.innerHTML = '<i class="fas fa-bars"></i>';
                    }
                }
            });
        });
    </script>
</body>
</html>
