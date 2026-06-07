MTS Stock Screener Dashboard
Momentum Trading Strategy (MTS) CAN SLIM Screener - Find the Biggest Explosive Winning Stocks in the Market 
A high-performance, single-page trading intelligence terminal designed to analyze, score, filter, and track structural momentum leaders. This dashboard is built entirely on the premium momentum trading methodologies popularized on the Trading Momentum Substack.

This tool integrates a real-time relative strength scoring matrix, structural Stage 2 trend analysis (inspired by legendary trader Mark Minervini), and an optional web-grounded AI intelligence engine powered by Gemini.

🚀 Key Features

Weighted Momentum Scoring System: Instantly ranks your watchlist by calculated momentum velocity across multiple horizons.

Minervini Trend Template Evaluator: Automatically evaluates every ticker against the $9$-point Stage 2 structural uptrend rules.

Unified, Responsive Grid Console: Features custom-built KPI indicators, search filters, sector filtering, bulk selection deletion, and a dynamic progress bar for background worker feedback.

Interactive Metric Cascade: Expand any stock card to reveal its detailed Relative Strength matrix breakdown and absolute moving average metrics.

MTS CSV Import/Export Engine: Seamlessly load your watchlists or download fully calculated reports ready for Excel or Google Sheets.

Web-Grounded Gemini AI Engine: Leverages gemini-2.5-flash-preview-09-2025 with real-time Google Search grounding to retrieve live, current-day indicators directly from the web without a paid third-party financial API.

Offline First & Caching: Saves your workspace automatically using local storage, keeping your watchlist secure in your browser.

📈 Methodology

1. The Momentum Ranking Formula

To isolate true market leaders, the terminal implements a multi-horizon momentum score. Recent velocity is weighted heavily while preserving intermediate-to-long-term trend confirmation:

$$\text{Momentum Score} = 0.4 \times M_3 + 0.2 \times M_6 + 0.2 \times M_9 + 0.2 \times M_{12}$$

Where:

$M_3$ = $3$-Month Price Performance ($\%$) (Weighted at $40\%$)

$M_6$ = $6$-Month Price Performance ($\%$) (Weighted at $20\%$)

$M_9$ = $9$-Month Price Performance ($\%$) (Weighted at $20\%$)

$M_{12}$ = $12$-Month Price Performance ($\%$) (Weighted at $20\%$)

2. Mark Minervini Stage 2 Trend Template

Every stock's structural health is assessed using a strict $9$-point trend compliance matrix:

Price over 50 SMA: Price must reside above the $50$-day Simple Moving Average.

Price over 150 SMA: Price must reside above the $150$-day Simple Moving Average.

Price over 200 SMA: Price must reside above the $200$-day Simple Moving Average.

50 SMA over 150 SMA: The $50$-day SMA must be higher than the $150$-day SMA.

50 SMA over 200 SMA: The $50$-day SMA must be higher than the $200$-day SMA.

150 SMA over 200 SMA: The $150$-day SMA must be higher than the $200$-day SMA.

Rising 200 SMA: The $200$-day SMA must be actively sloping upward (verified for at least $1$ month).

Near 52-Week High: Price must be within $25\%$ of its $52$-week high.

Clear of 52-Week Low: Price must be at least $30\%$ above its $52$-week low.

🛠️ Getting Started (Local Development)

Because this dashboard is engineered as a highly-optimized, zero-dependency static application, running it locally requires no build steps or package managers.

Option 1: Double-Click Run

Download or clone this repository to your machine.

Locate index.html.

Double-click to open it instantly in any modern web browser.

Option 2: Live Server (Recommended)

If you are using VS Code:

Install the Live Server extension.

Right-click index.html and select Open with Live Server.

🌐 Deploying to GitHub Pages

You can host this live tracker perpetually on GitHub Pages for free in under two minutes:

Create a New Repository: Name it something like mts-screener on your GitHub account and set it to Public.

Upload the Code: Push your code or upload index.html directly to the root folder of the repository.

Enable GitHub Pages:

Navigate to your repository's Settings tab.

In the left sidebar, click Pages.

Under Build and deployment, set the Source branch to main (or master) and click Save.

Access Your Dashboard: Your site will be online at https://<your-username>.github.io/mts-screener/ within a minute!

🧠 Web-Grounded AI Engine Setup

This terminal utilizes the Gemini API to search the live web and synthesize current price action, moving averages, and fundamental data.

How to use your own API Key:

Obtain a free/pay-as-you-go API Key from Google AI Studio.

Open index.html in a text editor.

Locate the following line at the top of the <script> block:

const apiKey = ""; // Runtime-injected token


Paste your key inside the empty quotes:

const apiKey = "YOUR_GEMINI_API_KEY_HERE";


Save the file. When you refresh or research stock records, the app will query real-time data using search-grounded queries.

Alternatively, keep Smart Demo Engine toggled ON to generate mock data based on realistic historic averages.

📊 CSV Export Format Schema

The exported CSV follows the standard MTS Screener report protocol, making it fully compatible with sheets designed around this methodology:

Column Name

Description

Values

Stock Name

Ticker Symbol

e.g. NVDA

Company Name

Full legal name

e.g. NVIDIA Corporation

Price

Current trading price

Float

P/E Ratio

Trailing Price-to-Earnings Ratio

Float or null

Match %

Percentage of compliance with core screening rules

Integer (0% to 100%)

Price > $10

Basic liquidity test

PASS ($value) / FAIL ($value)

Mkt Cap > $100M

Basic size filter

PASS ($value) / FAIL ($value)

Avg Vol > $100K

Basic liquidity check

PASS (value) / FAIL (value)

Qtrly EPS > 20%

Fundamental earnings check

PASS (value) / FAIL (value) / N/A

Qtrly Revenue > 20%

Fundamental sales check

PASS (value) / FAIL (value) / N/A

ROE > 15%

Management efficiency test

PASS (value) / FAIL (value) / N/A

Pre-Tax Margin > 15%

Structural profitability check

PASS (value) / FAIL (value) / N/A

RS Rating >= 80

Relative strength requirement

PASS (value) / FAIL (value)

Within 15% of 52W High

Standard trading consolidation check

PASS (value) / FAIL (value)

Price > 50-Day MA

Short term structural uptrend

PASS (Yes) / FAIL (No)

Price > 200-Day MA

Long term structural uptrend

PASS (Yes) / FAIL (No)

50MA > 200MA

Golden Cross criteria

PASS (Yes) / FAIL (No)

Pass/Fail

Master criteria evaluation

PASS (if 100% compliant) / FAIL

🛠️ Technology Stack

Styling: Tailwind CSS CSS Utility Engine (via CDN)

Icons: Font Awesome Web Icon Library

Typography: Google Fonts (Plus Jakarta Sans & JetBrains Mono)

Logic: Pure Vanilla ES6 JavaScript (zero builds, zero dependencies)

📝 License

This project is licensed under the MIT License - see the LICENSE file for details.
