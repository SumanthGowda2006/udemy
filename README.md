<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Udemy Clone - All in One</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #f7f9fa;
            color: #333;
            transition: background-color 0.3s, color 0.3s;
        }

        body.dark-mode {
            background: #333;
            color: #fff;
        }

        header {
            background: #fff;
            border-bottom: 1px solid #e5e5e5;
            padding: 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 10;
        }

        body.dark-mode header {
            background: #444;
        }

        .logo {
            height: 28px;
        }

        .search-bar {
            flex-grow: 1;
            margin: 0 1rem;
        }

        .search-bar input {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        nav a {
            margin: 0 0.5rem;
            text-decoration: none;
            color: #333;
            font-size: 14px;
        }

        .auth-btns button {
            margin-left: 0.5rem;
            padding: 0.4rem 0.8rem;
            border: 1px solid #333;
            background: transparent;
            border-radius: 4px;
            cursor: pointer;
        }

        .auth-btns .signup {
            background-color: #333;
            color: #fff;
            border: none;
        }

        .hero {
            padding: 2rem;
            background: #fff;
            text-align: center;
        }

        body.dark-mode .hero {
            background: #555;
        }

        .hero h1 {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }

        .hero p {
            color: #666;
            margin-bottom: 1rem;
        }

        .hero input {
            padding: 0.6rem;
            width: 80%;
            max-width: 400px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .courses {
            padding: 2rem 1rem;
        }

        .courses h2 {
            text-align: center;
            margin-bottom: 2rem;
            font-size: 1.5rem;
        }

        .course-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 1.5rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .course {
            background: #fff;
            border: 1px solid #ddd;
            border-radius: 6px;
            overflow: hidden;
            transition: transform 0.2s;
            cursor: pointer;
        }

        body.dark-mode .course {
            background: #444;
            border: 1px solid #666;
        }

        .course:hover {
            transform: translateY(-5px);
        }

        .course img {
            width: 100%;
            height: 140px;
            object-fit: cover;
        }

        .course-content {
            padding: 1rem;
        }

        .course-content h3 {
            font-size: 16px;
            margin-bottom: 0.5rem;
        }

        .course-content p {
            font-size: 14px;
            color: #666;
        }

        .rating {
            color: #f59e0b;
            font-weight: bold;
            margin-top: 0.5rem;
        }

        .price {
            font-weight: bold;
            margin-top: 0.5rem;
        }

        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: none;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            padding: 2rem;
            border-radius: 6px;
            width: 400px;
            text-align: center;
        }

        .modal h3 {
            margin-bottom: 1rem;
        }

        .modal p {
            margin-bottom: 1rem;
        }

        .modal button {
            padding: 0.5rem 1rem;
            background: #333;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .modal button:hover {
            background: #555;
        }

        .form-group {
            margin-bottom: 1rem;
            text-align: left;
        }

        .form-group input {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        @media (max-width: 600px) {
            .hero h1 {
                font-size: 1.5rem;
            }
        }
    </style>
</head>

<body>
    <header>
        <img src="https://www.udemy.com/staticx/udemy/images/v7/logo-udemy.svg" alt="Logo" class="logo" />
        <div class="search-bar">
            <input type="text" id="searchInput" placeholder="Search for anything" />
        </div>
        <nav>
            <a href="#categories">Categories</a>
            <a href="#business">Udemy Business</a>
            <a href="#teach">Teach</a>
            <a href="#mylearning">My Learning</a>
        </nav>
        <div class="auth-btns">
            <button id="loginBtn">Log in</button>
            <button class="signup" id="signupBtn">Sign up</button>
        </div>
        <button id="darkModeToggle">Toggle Dark Mode</button>
    </header>

    <section class="hero">
        <h1>Learn without limits</h1>
        <p>Choose from 210,000+ online video courses with new additions published every month</p>
        <input type="text" placeholder="What do you want to learn?">
    </section>

    <section class="courses">
        <h2>Featured Courses</h2>
        <div class="course-grid" id="courseGrid">
            <div class="course">
                <img src="https://img-c.udemycdn.com/course/240x135/1565838_e54e_18.jpg" alt="Web Development Bootcamp" />
                <div class="course-content">
                    <h3>2023 Web Development Bootcamp</h3>
                    <p>Colt Steele</p>
                    <div class="rating">4.7 ⭐</div>
                    <div class="price">₹449</div>
                </div>
            </div>
            <div class="course">
                <img src="https://img-c.udemycdn.com/course/240x135/567828_67d0.jpg" alt="JavaScript Guide" />
                <div class="course-content">
                    <h3>JavaScript: The Complete Guide</h3>
                    <p>Max Schwarzmüller</p>
                    <div class="rating">4.8 ⭐</div>
                    <div class="price">₹499</div>
                </div>
            </div>
            <div class="course">
                <img src="https://img-c.udemycdn.com/course/240x135/504800_3c68_3.jpg" alt="Python Bootcamp" />
                <div class="course-content">
                    <h3>Python for Everybody</h3>
                    <p>Charles Severance</p>
                    <div class="rating">4.9 ⭐</div>
                    <div class="price">₹499</div>
                </div>
            </div>
            <div class="course">
                <img src="https://img-c.udemycdn.com/course/240x135/1040288_16b9_3.jpg" alt="Data Science" />
                <div class="course-content">
                    <h3>Data Science A-Z™: Real-Life Data Science</h3>
                    <p>Kirill Eremenko</p>
                    <div class="rating">4.8 ⭐</div>
                    <div class="price">₹599</div>
                </div>
            </div>
            <div class="course">
                <img src="https://img-c.udemycdn.com/course/240x135/1200516_b3a1_3.jpg" alt="Machine Learning" />
                <div class="course-content">
                    <h3>Machine Learning A-Z™: Hands-On Python & R In Data Science</h3>
                    <p>Kirill Eremenko</p>
                    <div class="rating">4.7 ⭐</div>
                    <div class="price">₹699</div>
                </div>
            </div>
            <div class="course">
                <img src="https://img-c.udemycdn.com/course/240x135/328200_2b54_6.jpg" alt="Complete React Developer" />
                <div class="course-content">
                    <h3>Complete React Developer in 2023</h3>
                    <p>Andrei Neagoie</p>
                    <div class="rating">4.9 ⭐</div>
                    <div class="price">₹499</div>
                </div>
            </div>
        </div>
    </section>

    <section class="courses">
        <h2>Recommended for You</h2>
        <div class="course-grid" id="recommendedCourses">
            <!-- Recommended courses will be dynamically added here -->
        </div>
    </section>

    <!-- Course Modal -->
    <div class="modal" id="courseModal">
        <div class="modal-content">
            <h3 id="courseTitle">Course Title</h3>
            <p id="courseInstructor">Instructor Name</p>
            <p id="coursePrice">₹499</p>
            <p id="courseDescription">Course Description</p>
            <button id="closeModal">Close</button>
        </div>
    </div>

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <h3>Log In</h3>
            <div class="form-group">
                <input type="email" placeholder="Email" required />
            </div>
            <div class="form-group">
                <input type="password" placeholder="Password" required />
            </div>
            <button id="loginSubmit">Log In</button>
            <button id="closeLoginModal">Close</button>
        </div>
    </div>

    <!-- Sign Up Modal -->
    <div class="modal" id="signupModal">
        <div class="modal-content">
            <h3>Sign Up</h3>
            <div class="form-group">
                <input type="text" placeholder="Full Name" required />
            </div>
            <div class="form-group">
                <input type="email" placeholder="Email" required />
            </div>
            <div class="form-group">
                <input type="password" placeholder="Password" required />
            </div>
            <button id="signupSubmit">Sign Up</button>
            <button id="closeSignupModal">Close</button>
        </div>
    </div>

    <script>
        // Course data array (for dynamic generation)
        const courses = [
            { title: "2023 Web Development Bootcamp", instructor: "Colt Steele", image: "https://img-c.udemycdn.com/course/240x135/1565838_e54e_18.jpg", rating: 4.7, price: "₹449", description: "Learn web development from scratch." },
            { title: "JavaScript: The Complete Guide", instructor: "Max Schwarzmüller", image: "https://img-c.udemycdn.com/course/240x135/567828_67d0.jpg", rating: 4.8, price: "₹499", description: "Master JavaScript with this complete guide." },
            { title: "Python for Everybody", instructor: "Charles Severance", image: "https://img-c.udemycdn.com/course/240x135/504800_3c68_3.jpg", rating: 4.9, price: "₹499", description: "Learn Python programming from scratch." },
            { title: "Data Science A-Z™: Real-Life Data Science", instructor: "Kirill Eremenko", image: "https://img-c.udemycdn.com/course/240x135/1040288_16b9_3.jpg", rating: 4.8, price: "₹599", description: "Learn how to become a data scientist." },
            { title: "Machine Learning A-Z™: Hands-On Python & R In Data Science", instructor: "Kirill Eremenko", image: "https://img-c.udemycdn.com/course/240x135/1200516_b3a1_3.jpg", rating: 4.7, price: "₹699", description: "Master Machine Learning with Python and R." },
            { title: "Complete React Developer in 2023", instructor: "Andrei Neagoie", image: "https://img-c.udemycdn.com/course/240x135/328200_2b54_6.jpg", rating: 4.9, price: "₹499", description: "Become a React developer from scratch." },
        ];

        const courseGrid = document.getElementById("courseGrid");

        courses.forEach(course => {
            const courseCard = document.createElement("div");
            courseCard.classList.add("course");

            courseCard.innerHTML = `
                <img src="${course.image}" alt="${course.title}" />
                <div class="course-content">
                    <h3>${course.title}</h3>
                    <p>${course.instructor}</p>
                    <div class="rating">${course.rating} ⭐</div>
                    <div class="price">${course.price}</div>
                </div>
            `;

            courseCard.addEventListener("click", () => {
                openModal(course);
            });

            courseGrid.appendChild(courseCard);
        });

        // Function to open course modal
        function openModal(course) {
            document.getElementById("courseTitle").innerText = course.title;
            document.getElementById("courseInstructor").innerText = course.instructor;
            document.getElementById("coursePrice").innerText = course.price;
            document.getElementById("courseDescription").innerText = course.description;
            document.getElementById("courseModal").style.display = "flex";
        }

        document.getElementById("closeModal").addEventListener("click", () => {
            document.getElementById("courseModal").style.display = "none";
        });

        // Show login modal
        document.getElementById("loginBtn").addEventListener("click", () => {
            document.getElementById("loginModal").style.display = "flex";
        });

        // Show signup modal
        document.getElementById("signupBtn").addEventListener("click", () => {
            document.getElementById("signupModal").style.display = "flex";
        });

        // Close login modal
        document.getElementById("closeLoginModal").addEventListener("click", () => {
            document.getElementById("loginModal").style.display = "none";
        });

        // Close signup modal
        document.getElementById("closeSignupModal").addEventListener("click", () => {
            document.getElementById("signupModal").style.display = "none";
        });

        // Dark mode toggle
        document.getElementById("darkModeToggle").addEventListener("click", () => {
            document.body.classList.toggle("dark-mode");
            localStorage.setItem("darkMode", document.body.classList.contains("dark-mode"));
        });

        // On page load
        if (localStorage.getItem("darkMode") === "true") {
            document.body.classList.add("dark-mode");
        }

        // Search functionality
        document.getElementById('searchInput').addEventListener('input', function() {
            const query = this.value.toLowerCase();
            const courseCards = document.querySelectorAll('.course');
            
            courseCards.forEach(card => {
                const title = card.querySelector('h3').innerText.toLowerCase();
                card.style.display = title.includes(query) ? 'block' : 'none';
            });
        });

        // Function for recommended courses
        function recommendCourses() {
            const recommendedCourses = courses.filter(course => course.rating > 4.7); // Example criteria
            const recommendedGrid = document.getElementById("recommendedCourses");

            recommendedCourses.forEach(course => {
                const courseCard = document.createElement("div");
                courseCard.classList.add("course");

                courseCard.innerHTML = `
                    <img src="${course.image}" alt="${course.title}" />
                    <div class="course-content">
                        <h3>${course.title}</h3>
                        <p>${course.instructor}</p>
                        <div class="rating">${course.rating} ⭐</div>
                        <div class="price">${course.price}</div>
                    </div>
                `;

                courseCard.addEventListener("click", () => {
                    openModal(course);
                });

                recommendedGrid.appendChild(courseCard);
            });
        }

        // Call recommendCourses to populate recommendations
        recommendCourses();
    </script>
</body>

</html>
