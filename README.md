# Passive Portfolio Workflow

A single-page tool for building a passive portfolio in three stages:

1. **Define the Investable Universe** – pick from 729 US stocks, ETFs, index funds and Shariah-compliant funds, and check access, cost and liquidity.
2. **Analyse Historical Behaviour** – growth, swing, skewness, kurtosis, worst month, max drawdown, losing months/years, Sharpe ratio, histogram and correlations.
3. **Simulate Future Outcomes** – Monte Carlo simulation that draws real months from history, with fees, a fan chart and a crisis stress test.

It is a static site: everything (data included) is in `index.html`. There is no server, database or API key. Each visitor's list is saved in their own browser only.

## Deploy to Vercel

**Option A – drag and drop (no tools needed)**
1. Unzip this folder.
2. Go to https://vercel.com/new, sign in, and choose to deploy a project without Git (or drag the folder onto the Vercel dashboard).
3. Leave the framework as "Other", with no build command and no output directory.
4. Click Deploy. You get a link like `https://your-project.vercel.app` to share.

**Option B – GitHub (best if you'll update it)**
1. Create a new GitHub repository and upload these files.
2. In Vercel, click **Add New → Project**, import the repository, keep the default settings (Framework: Other, no build command), and click Deploy.
3. Every time you push a change, Vercel redeploys automatically.

**Option C – Vercel CLI**
```bash
npm i -g vercel
cd passive-portfolio-workflow
vercel          # preview deployment
vercel --prod   # production deployment
```

## Run locally
Open `index.html` in a browser, or run `npx serve .` in this folder.

## Data and limits
- Monthly total returns (dividends included), running to October 2026. The data does not update by itself.
- Sources: the open sp500-data project (github.com/Johnbrick123/sp500-data, built from Yahoo Finance and CRSP), the open fund-compare project (github.com/jdlemay/fund-compare, built from Yahoo Finance), Digrin (digrin.com) for 11 Shariah-compliant funds, and Aswath Damodaran (NYU Stern) T-bill rates for the Sharpe ratio.
- Stocks are today's S&P 500 members only, so companies that left the index are missing.
- Charts load Chart.js 4.4.1 from cdnjs, and the Inter font from Google Fonts.
- Before sharing publicly, check that you are comfortable with the data sources' terms of use. This tool is for education, not financial advice.
