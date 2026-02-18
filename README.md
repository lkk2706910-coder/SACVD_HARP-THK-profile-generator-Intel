# SACVD_HARP-THK-profile-generator
SACVD_HARP THK profile generator
##################################################
# Wafer Map Pro v11 - SACVD/HARP Profile Generator

**Wafer Map Pro** is a lightweight, browser-based tool designed for visualizing and analyzing semiconductor wafer thickness profiles (specifically for SACVD/HARP processes). It allows users to input measurement data, visualize 2D contour maps, and compare fleet-wide performance across multiple slots.

![Wafer Map Pro Screenshot](https://via.placeholder.com/800x450?text=Wafer+Map+Pro+Screenshot) *(Optional: Replace this link with a real screenshot of your tool)*

## 🚀 Key Features

* **Interactive Wafer Maps**: Generates high-quality 2D contour plots using Plotly.js to visualize thickness uniformity.
* **49-Point Measurement Support**: Pre-configured coordinate system for standard 49-point measurement recipes (SACVD/HARP).
* **Multi-Slot Management**: Switch seamlessly between 5 different slots (A, B, C, D, E) to manage data for a full batch.
* **Smart Data Parsing**: 
    * One-click "Parse Data" feature automatically extracts numerical values from raw text (e.g., copied from Excel columns).
    * Auto-assigns values to the correct measurement points.
* **Real-time Statistics**: Instantly calculates and displays key metrology stats in a clear, vertical layout:
    * **THK (Avg)**: Average Thickness (Å)
    * **RANGE**: Max - Min (Å)
    * **UNIFORMITY**: Coefficient of Variation (CV%) = (StdDev / Mean) * 100
    * **MAX**: Maximum value (Å)
    * **MIN**: Minimum value (Å)
* **Fleet Comparison View**: A dedicated dashboard to view and compare maps and statistics for all 5 slots simultaneously.
* **Responsive Design**: Built with Tailwind CSS for a clean, modern UI that adjusts to different screen sizes.

## 🛠️ Technology Stack

* **HTML5 / JavaScript (ES6)**: Pure client-side logic, no backend required.
* **[Plotly.js](https://plotly.com/javascript/)**: Used for rendering the complex contour/heatmap visualizations.
* **[Tailwind CSS](https://tailwindcss.com/)**: Used for rapid, utility-first styling.

## 📦 Installation & Usage

This tool is a static web application. You can run it directly from your computer or host it on any static site provider (like GitHub Pages).

### Option 1: Run Locally
1.  Clone this repository or download the ZIP file.
2.  Ensure the following files are in the same directory:
    * `index.html` (The main application file)
    * `plotly-2.24.1.min.js` (Plotly library)
    * `tailwindcss.js` (Tailwind library)
3.  Open `index.html` in any modern web browser (Chrome, Edge, Firefox).

### Option 2: Host on GitHub Pages
1.  Upload all files (`index.html`, `.js` files) to a GitHub repository.
2.  Go to **Settings** > **Pages**.
3.  Select the `main` branch as the source and click **Save**.
4.  Your tool will be live at `https://<your-username>.github.io/<repo-name>/`.

## 📊 Statistical Formulas

The tool calculates uniformity using the **Coefficient of Variation (CV)** method, commonly used in semiconductor metrology:

$$\text{Uniformity (\%)} = \left( \frac{\sigma}{\mu} \right) \times 100$$

Where:
* $\sigma$ = Sample Standard Deviation (1-Sigma)
* $\mu$ = Mean (Average) Thickness

## 📝 Configuration

The coordinate system is hardcoded for a specific 49-point recipe. To modify the measurement points, edit the `config` object in the `<script>` section of `index.html`:

```javascript
const config = {
    X: [0.0, 0.0001, ...], // Array of X coordinates
    Y: [0.0, -49.3332, ...] // Array of Y coordinates
};
