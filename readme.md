# **MTS Stock Screener Dashboard**

A premium, high-performance, single-page trading intelligence terminal designed to analyze, score, filter, and track structural momentum leaders. This dashboard is built entirely around the momentum trading methodologies popularized on the [Trading Momentum Substack](https://tradingmomentum.substack.com).

This tool integrates a real-time relative strength scoring matrix, structural Stage 2 trend analysis (inspired by legendary trader Mark Minervini), and an optional web-grounded AI intelligence engine powered by Gemini.

## **🚀 Key Features**

* **Weighted Momentum Scoring System:** Instantly ranks your watchlist by calculated momentum velocity across multiple horizons.  
* **Minervini Trend Template Evaluator:** Automatically evaluates every ticker against the 9-point Stage 2 structural uptrend rules.  
* **Unified, Responsive Grid Console:** Features custom-built KPI indicators, search filters, sector filtering, bulk selection deletion, and a dynamic progress bar for background worker feedback.  
* **Interactive Metric Cascade:** Expand any stock card to reveal its detailed Relative Strength matrix breakdown and absolute moving average metrics.  
* **MTS CSV Import/Export Engine:** Seamlessly load your watchlists or download fully calculated reports ready for Excel or Google Sheets.  
* **Web-Grounded Gemini AI Engine:** Leverages gemini-2.5-flash-preview-09-2025 with real-time Google Search grounding to retrieve live, current-day indicators directly from the web without a paid third-party financial API.  
* **Offline First & Caching:** Saves your workspace automatically using local storage, keeping your watchlist secure in your browser.

## **📈 Methodology**

### **1\. The Momentum Ranking Formula**

To isolate true market leaders, the terminal implements a multi-horizon momentum score. Recent velocity is weighted heavily while preserving intermediate-to-long-term trend confirmation:

![][image1]Where:

* ![][image2] \= 3-Month Price Performance (%) *(Weighted at 40%)*  
* *![][image3]* \= 6-Month Price Performance (%) *(Weighted at 20%)*  
* *![][image4]* \= 9-Month Price Performance (%) *(Weighted at 20%)*  
* *![][image5]* \= 12-Month Price Performance (%) *(Weighted at 20%)*

### **2\. Mark Minervini Stage 2 Trend Template**

Every stock's structural health is assessed using a strict 9-point trend compliance matrix:

1. **Price over 50 SMA:** Price must reside above the 50-day Simple Moving Average.  
2. **Price over 150 SMA:** Price must reside above the 150-day Simple Moving Average.  
3. **Price over 200 SMA:** Price must reside above the 200-day Simple Moving Average.  
4. **50 SMA over 150 SMA:** The 50-day SMA must be higher than the 150-day SMA.  
5. **50 SMA over 200 SMA:** The 50-day SMA must be higher than the 200-day SMA.  
6. **150 SMA over 200 SMA:** The 150-day SMA must be higher than the 200-day SMA.  
7. **Rising 200 SMA:** The 200-day SMA must be actively sloping upward (verified for at least 1 month).  
8. **Near 52-Week High:** Price must be within 25% of its 52-week high.  
9. **Clear of 52-Week Low:** Price must be at least 30% above its 52-week low.

## **🛠️ Getting Started (Local Development)**

Because this dashboard is engineered as a highly-optimized, zero-dependency static application, running it locally requires no build steps or package managers.

### **Option 1: Double-Click Run**

1. Download or save this folder to your machine.  
2. Locate index.html.  
3. Double-click to open it instantly in any modern web browser.

### **Option 2: VS Code Live Server (Recommended)**

1. Install the **Live Server** extension inside VS Code.  
2. Right-click index.html and select **Open with Live Server**.

## **☁️ Deploying to GitHub Pages**

You can host this live tracker perpetually on GitHub Pages for free in under two minutes:

1. **Create a New Repository:** Name it something like mts-screener on your GitHub account and set it to **Public**.  
2. **Upload the Code:** Upload index.html directly to the root folder of the repository.  
3. **Enable GitHub Pages:**  
   * Navigate to your repository's **Settings** tab.  
   * In the left sidebar, click **Pages**.  
   * Under "Build and deployment", set the Source branch to main (or master) and click **Save**.  
4. **Access Your Dashboard:** Your site will be online at:  
   https://\<your-username\>.github.io/mts-screener/

## **🤖 Web-Grounded AI Engine Setup**

This terminal utilizes the Gemini API to search the live web and synthesize current price action, moving averages, and fundamental data.

### **How to use your own API Key:**

1. Obtain a free/pay-as-you-go API Key from [Google AI Studio](https://aistudio.google.com/).  
2. Open index.html in a text editor.  
3. Locate the following line at the top of the \<script\> block:  
   const apiKey \= ""; // Runtime-injected token

4. Paste your key inside the empty quotes:  
   const apiKey \= "YOUR\_GEMINI\_API\_KEY\_HERE";

5. Save the file. When you refresh or research stock records, the app will query real-time data using search-grounded queries.  
6. Alternatively, keep the **Smart Demo Engine** toggled ON to generate mock data based on realistic historic averages.

## **📊 CSV Export Format Schema**

The exported CSV follows the standard MTS Screener report protocol, making it fully compatible with sheets designed around this methodology. It contains the following structural columns:

* **Stock Name:** Ticker Symbol  
* **Company Name:** Full company name  
* **Price:** Current close price  
* **P/E Ratio:** Trailing P/E  
* **Match %:** Percentage of screening compliance out of 12 rules  
* **Price \> $10:** Liquidity test *(PASS/FAIL)*  
* **Mkt Cap \> $100M:** Size filter *(PASS/FAIL)*  
* **Avg Vol \> $100K:** Liquidity check *(PASS/FAIL)*  
* **Qtrly EPS \> 20%:** Earnings growth *(PASS/FAIL)*  
* **Qtrly Revenue \> 20%:** Revenue growth *(PASS/FAIL)*  
* **ROE \> 15%:** Return on Equity check *(PASS/FAIL)*  
* **Pre-Tax Margin \> 15%:** Net margins *(PASS/FAIL)*  
* **RS Rating \>= 80:** Momentum relative strength *(PASS/FAIL)*  
* **Within 15% of 52W High:** Consolidation check *(PASS/FAIL)*  
* **Price \> 50-Day MA:** Short-term trend *(PASS/FAIL)*  
* **Price \> 200-Day MA:** Long-term trend *(PASS/FAIL)*  
* **50MA \> 200MA:** Golden Cross check *(PASS/FAIL)*  
* **Pass/Fail:** Final status *(PASS if 100% compliant)*

## **💻 Technology Stack**

* **Styling:** Tailwind CSS Utility Engine (via CDN)  
* **Icons:** Font Awesome Web Icon Library  
* **Typography:** Google Fonts (Plus Jakarta Sans & JetBrains Mono)  
* **Logic:** Pure Vanilla ES6 JavaScript (zero builds, zero dependencies)

## **📄 License**

This project is licensed under the MIT License.

[image1]: <data:image/png;base64,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>

[image2]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABwAAAAaCAYAAACkVDyJAAACF0lEQVR4Xu2UT0jUQRTHd2GT/ggmtS3sv9k/SLSChUuHoJN08WBg3cR7BAriJdhDpyI9CyJCUEEEUdClQ+DBu5cOiVcPgngVDDxkfr7ujLyGlXZpu8h+4ct7v3nfeTPz3swvkejhXCGXy10rlUqLzrlVEf9OrLEol8sj6JaNfgFejXVnol6vXyBJhskz8IjJT2JNQKVSGUDzFf6CG8y7rQ0TSsbav0ILFYvFNyRqxLEA4rNwBc1v7LM43jay2ex1knyEt+B6Op3ut3FVgfEXnOgmdg1u5/P5nNV0BHZbJ8lr7CB2UxuwccYmReIV7K7KSkUuWk1HUDlD75RQiUOMHuV1On/K8X8uJ0iSZJkk9/WB/7NQKNw1sQaxYR97CY/4fnA6u1OE/oUy+hNMyNcmOPlT+eorsXXXun/a2GhbZQ79w03pWwvCeT0BYq9kva5l/1j8kn/HY3ATPgqxlrD9E5hwAJfgTCizQJkf+tP/0T+/4X355HmLv5bJZK5YjUUKwTubmO8duM3Y84R50O6M/ik541OJZq5P8IN8qzkFwVH4nbIMmbENuKXbGcZM/3bsuEGSjUxrLm/VxUElvQcPXbNfJ2TCl1qt1of/GT6Wzj/0Pavz2m9csssmZYpyzhF7jy2Z8f8L1yz7j2q1eiOOdQ0sMKZbKl8Xiu8DXaRY1zX4RfbkYxuueenKsa6r8L+99h5+Dz20g2Mbt5C4ddkA2AAAAABJRU5ErkJggg==>

[image3]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABwAAAAaCAYAAACkVDyJAAACGElEQVR4Xu2UPWhUQRSFN5gEEwUjcbOwf29/CCErJCFLCsHSxmIF1zKQVoTY2ARSWBk0lYUQRBAkZSCQxkLYImUgjUWClbDFglhZKVi48TvZGbkZ8tBNso3sgcPcuffMnZl737xEoo//CplMZrxQKKxHUfRGxJ4LNRbFYnEG3YbRv4BjoS4W1Wp1iCQpFi/DNosfhhqPUql0Dc17+Avus25WByY0EGr/Cm2Uz+ffkWg1jHkQfwxfozliXAnj/4x0On2DJFtwGu4mk8mrNq4q4H/GjaYYG7CZzWYzVtMVOG2VJG8ZrzMe6gA2ju++SLzE+EVlpSKXraYrqJy+d0qoxD5Gj7K6nbvl3XOXEwyQZIMktzXB/pHL5RZMbJXYTRdbg23md/6s7ha+f76M7gY12ToEN38kW30lthvF9A//tFqDeSmMnYDvH+ag5toQPtETIPZco9PF9s+VvY5mCb70uU6F7Z/Awu/wFVz2ZRYo8z13+xP947Yj+Ldl6yeA3UilUlesxmIQwaZNzLwFm/ieJsyDjmL6pzn+z9YXC4Tz8COnnDS+ffhJZfI+07+W9Qu6Mf6DqPOnahRO+zUSuAV/Rp1+HZOFO5VKZRh7Gz6Qzj30r1bntB/4yEalcRt+c3nrcM/3vSdwGx6XVK3RAfOdr7U3YINFeChb7xe71dMNXdn3ZLNRDfugXC5PhLoLBxvNhz/9Pvo4M34DB4KSrtVPQaYAAAAASUVORK5CYII=>

[image4]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABwAAAAaCAYAAACkVDyJAAACEUlEQVR4Xu2VP0ibQRjGv4AWEUHFBiH/viQg0ghamjoojg7tYEE7O2tBF5eCSCdFRegiSCkUiqNQ6uIgOAQcs7i0Di4iQhFnCx3883uaOzmvCRobF8kDD/d+9z73vnfve5cEQR2PCvF4vCOdTi+HYfhZxH7ua1xkMpledGuOfgm2+bqKyOfzjQTpZPEUvGDxhK+xyGazrWi24Dkssq5PG8YV8bW3QolSqdRXAs36Pgv80/ATmkvG977/zojFYk8JsgGfwUI0Gm1x/aoC8/OcqJtxBx4mEom4q6kK7DZPkC+M7Yw/tAHXz9yoiD/L+EtlpSJNrqYqqJy2dwqowNZHjxI6nTnl6/8uJ4gQZI0gQ/rA/p1MJvsd3yy+HuNbgBd8D1+vrha2f7aM5gQjsrUJTv5OtvqKrxBW6B/zg3cqs+0fZoO+lRDO6AngW9RodGX7Z0q9YuJ8pzovra8s3P4JLDqDq3DKllkg0Btz+hv9Y+0r5g9kM475G/LRgGDdDcz3MTxk7kPgPOiwQv+0AeYLxh4JvUt3AzhfwD160uXMFeG+bqedc/p37M4LJuGusZXwTOV1NQo6AP+EpX79JaLNXC73BPsbfCudeegnrs5ot7lkzU6sn7JN8n8T1hgREoyTaA5+hKf6jfVFD4KwdGmKbKDd99UMOg0JjoLSj8QqN3TS19QcegY8m1hwn7+pOuoohyvfRJPFC8v8XAAAAABJRU5ErkJggg==>

[image5]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACMAAAAaCAYAAAA9rOU8AAACU0lEQVR4Xu2VvWtUQRTF38MVFD+I6Lpkv+Y9d2ERbWRBFAKKWmihoK3YWChoIRiCkC5gQEVBxEJECPovBBuxiFgIBsTGUlAQUogIgjZC4u/kzWyGYeOG7Ev3Dhxm5t67d87MvW82igoUGAJJkmwxxkzAp2Kz2byCOQ7jfBBz0sXz+ztwJIxZL+JarbabDcZIvgTnyuXy9jDIgY0TYj7AxUajcbDVau3FvCmMGwqI6bLPezb5CkdDv9Dtdjfjm7a3shT680KMmBm70SLzU2GAbgTctTfzBc6HMbmgWq3uIfksvKkTw4u+397IbUQekFAJhs/8mNxg++UF41krZtL3s74AL9v5ZD/BuYGbvyqqb9jkN/Pnzkdz17E9qNfrW5Psy3sJf8D9fo68ULK3MmY3/mZWvqgSAqZUHgUy7sO3AN92Op0dfhLiRtrt9k7fBmL1mJ6CwN4fnLhG8ln1DT/axXwefrJrlW25PAKf8jmTleiRNZXUQ/CJDqGbdbG2z+6ZrA+vwfFowPul0yrZTJSdwpVhgfkxxsf+myMREiNR1rT8RmFL4UdfDOujrN8YW06zltISMK1+cWv1C7a/NtEhZ5co1nMSqnI5u4BtNBRDniPYvjMetzG/4Jnej0KongS8YzjtbCS8ZbJS6Fp70GuL7Sd8XalUtvm+fmJCmKwX09AepWl6GMcfu6njZ/nUJ4h75cpjVt6ekL13xgwQY/9uLoX2DcH/xKiROdzDaFDz5oXVxEgIthv4TqjMVKTj+zcEq4iJsV2H563/vhn0NRUoUGAI/AN6MqYGD/Z0GwAAAABJRU5ErkJggg==>