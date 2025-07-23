<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emergency Dashboard - Interactive README</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6; /* Light gray background */
            color: #333;
        }
        .container {
            max-width: 960px;
            margin: 2rem auto;
            padding: 2rem;
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        .btn {
            @apply px-6 py-3 rounded-lg font-semibold transition-all duration-300 ease-in-out;
        }
        .btn-primary {
            @apply bg-blue-600 text-white hover:bg-blue-700 shadow-md;
        }
        .btn-secondary {
            @apply bg-gray-200 text-gray-800 hover:bg-gray-300;
        }
        .section-title {
            @apply text-2xl font-bold text-gray-800 mb-4;
        }
        .metric-card {
            @apply bg-blue-50 p-4 rounded-lg shadow-sm flex flex-col items-center justify-center text-center;
        }
        .metric-value {
            @apply text-3xl font-bold text-blue-700;
        }
        .metric-label {
            @apply text-sm text-gray-600 mt-1;
        }
        /* Modal styles */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
        }
        .modal.show {
            opacity: 1;
            visibility: visible;
        }
        .modal-content {
            background-color: #ffffff;
            padding: 1.5rem;
            border-radius: 12px;
            max-width: 90%;
            max-height: 90%;
            overflow: auto;
            position: relative;
        }
        .modal-content img {
            max-width: 100%;
            height: auto;
            display: block; /* Remove extra space below image */
            border-radius: 8px;
        }
        .close-button {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 2rem;
            color: #555;
            cursor: pointer;
            background: none;
            border: none;
            padding: 0;
            line-height: 1;
        }
        .expandable-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-out;
        }
        .expandable-content.expanded {
            max-height: 500px; /* Adjust as needed for content height */
        }
    </style>
</head>
<body class="antialiased">
    <div class="container">
        <header class="text-center mb-8">
            <h1 class="text-4xl font-extrabold text-gray-900 mb-2">🏥 Harshit Bihani Emergency Room Visits Dashboard</h1>
            <p class="text-lg text-gray-600">A comprehensive overview of ER operations and patient insights.</p>
        </header>

        <section class="mb-8">
            <h2 class="section-title">📊 Dashboard Overview</h2>
            <p class="text-gray-700 leading-relaxed mb-6">
                This interactive dashboard provides real-time insights into Emergency Room (ER) visit data, helping to optimize patient flow, improve wait times, and enhance overall patient satisfaction. Explore key metrics and trends at a glance.
            </p>
            <div class="flex flex-col items-center justify-center space-y-4 md:space-y-0 md:flex-row md:space-x-4">
                <button id="viewDashboardBtn" class="btn btn-primary">View Dashboard Screenshot</button>
                <a href="#" class="btn btn-secondary" target="_blank" rel="noopener noreferrer">
                    <span class="mr-2">🔗</span>Link to Tableau Public (if available)
                </a>
            </div>
        </section>

        <section class="mb-8">
            <h2 class="section-title">✨ Key Metrics at a Glance</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="metric-card">
                    <div class="metric-value">9,216</div>
                    <div class="metric-label">Patients Visiting ER</div>
                </div>
                <div class="metric-card">
                    <div class="metric-value">35.26 min</div>
                    <div class="metric-label">Average Wait Time</div>
                </div>
                <div class="metric-card">
                    <div class="metric-value">4.99/10</div>
                    <div class="metric-label">Average Patient Satisfaction</div>
                </div>
            </div>
        </section>

        <section class="mb-8">
            <h2 class="section-title">🚀 Getting Started</h2>
            <p class="text-gray-700 leading-relaxed mb-4">
                To view and interact with the full Tableau dashboard, you will need Tableau Desktop or Tableau Public.
            </p>
            <h3 class="text-xl font-semibold text-gray-800 mb-2">Prerequisites:</h3>
            <ul class="list-disc list-inside text-gray-700 ml-4 mb-4">
                <li>Tableau Desktop (preferred for full functionality) or Tableau Public (free, view-only).</li>
            </ul>
            <h3 class="text-xl font-semibold text-gray-800 mb-2">Installation and Usage:</h3>
            <ol class="list-decimal list-inside text-gray-700 ml-4">
                <li class="mb-2">
                    **Clone the repository:**
                    <pre class="bg-gray-100 p-3 rounded-md text-sm mt-1 overflow-x-auto"><code>git clone https://github.com/YourUsername/YourRepositoryName.git
cd YourRepositoryName</code></pre>
                    <p class="text-xs text-gray-500 mt-1">*(Replace `YourUsername/YourRepositoryName` with the actual path to your repository.)*</p>
                </li>
                <li class="mb-2">
                    **Open the Tableau Workbook:**
                    <p>Open `ER Main.twbx` (Tableau Packaged Workbook) directly with Tableau Desktop. This file includes the data source internally.</p>
                    <p>Alternatively, you can open `ER Main.twb` (Tableau Workbook) and connect it to the `Hospital ER.csv` data source if they are in the same directory.</p>
                </li>
                <li>
                    **Explore the Dashboard:**
                    <p>Once opened, you can interact with the various filters and visualizations to gain insights.</p>
                </li>
            </ol>
        </section>

        <section class="mb-8">
            <h2 class="section-title">📁 Project Structure</h2>
            <ul class="list-disc list-inside text-gray-700 ml-4">
                <li>`ER Main.twb`: The main Tableau workbook file.</li>
                <li>`ER Main.twbx`: The Tableau packaged workbook, including the data source. This is the easiest file to open and share.</li>
                <li>`Hospital ER.csv`: The raw data source used for the dashboard.</li>
                <li>`ER Dashboard.png`: A screenshot of the dashboard for quick reference.</li>
                <li>`index.html`: This interactive README file.</li>
            </ul>
        </section>

        <section class="mb-8">
            <h2 class="section-title">🛠️ Built With</h2>
            <ul class="list-disc list-inside text-gray-700 ml-4">
                <li><a href="https://www.tableau.com/" class="text-blue-600 hover:underline" target="_blank" rel="noopener noreferrer">Tableau Desktop</a> - Data Visualization Software</li>
                <li><a href="https://tailwindcss.com/" class="text-blue-600 hover:underline" target="_blank" rel="noopener noreferrer">Tailwind CSS</a> - For styling and responsiveness</li>
                <li>HTML, CSS, JavaScript</li>
            </ul>
        </section>

        <section>
            <h2 class="section-title">📧 Contact</h2>
            <p class="text-gray-700">For any questions or feedback, please contact Harshit Bihani.</p>
        </section>
    </div>

    <!-- Dashboard Image Modal -->
    <div id="dashboardModal" class="modal">
        <div class="modal-content">
            <button class="close-button" id="closeModalBtn">&times;</button>
            <img src="https://placehold.co/900x600/E0F2F7/000000?text=ER+Dashboard+Screenshot" alt="Emergency Dashboard Screenshot" onerror="this.onerror=null;this.src='https://placehold.co/900x600/E0F2F7/000000?text=Image+Not+Found';" />
            <p class="text-center text-sm text-gray-500 mt-2">Full view of the Emergency Dashboard.</p>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const viewDashboardBtn = document.getElementById('viewDashboardBtn');
            const dashboardModal = document.getElementById('dashboardModal');
            const closeModalBtn = document.getElementById('closeModalBtn');
            const dashboardImage = dashboardModal.querySelector('img');

            // Set the actual image source for the modal
            // IMPORTANT: Replace 'ER%20Dashboard.png' with the actual path to your image
            // If you uploaded it to GitHub, it might be a raw URL like:
            // 'https://raw.githubusercontent.com/YourUsername/YourRepositoryName/main/ER%20Dashboard.png'
            dashboardImage.src = 'ER%20Dashboard.png'; // Assuming it's in the same directory

            viewDashboardBtn.addEventListener('click', () => {
                dashboardModal.classList.add('show');
            });

            closeModalBtn.addEventListener('click', () => {
                dashboardModal.classList.remove('show');
            });

            // Close modal when clicking outside the content
            dashboardModal.addEventListener('click', (event) => {
                if (event.target === dashboardModal) {
                    dashboardModal.classList.remove('show');
                }
            });
        });
    </script>
</body>
</html>
