# Taiwan-Stock-Prediction-App 📈

Welcome to the `Taiwan-Stock-Prediction-App` repository! This web application is designed to provide deep analytical insights into the Taiwanese stock market, with a special focus on prominent ETFs such as 00881, 00878, and 0050. Utilizing cutting-edge algorithms, it processes extensive stock data and news to deliver impactful analysis on the semiconductor industry and AI sector advancements. Our predictive models are at the core of the app, offering estimations on stock trends and actionable trading recommendations.

[LINK](https://jackyleedesign.github.io/chatGPT-taiwan-stocks-prediction/)

![image](https://raw.githubusercontent.com/JackyLeeDesign/chatGPT-taiwan-stocks-prediction/main/demo.png)

## 🚨 Important Disclaimer:
Please note that investing in stocks carries inherent risks, including the potential for loss. The creators of this website will not be held responsible for any financial outcomes. All content provided herein is for educational purposes only. We strongly advise users to perform thorough research and exercise caution when making investment decisions.

---

# Define prompt for GPT-o3-mini 🤖
The following prompt was crafted to interact with GPT-o3-mini, aiming to simulate a scenario where a financial analyst (played by GPT-4) provides stock price predictions and technical analysis:

```python
# Define prompt for GPT-4  
prompt = (  
   f"""
        You are a financial analyst, and I am your client. Please provide a concise stock analysis and trading suggestions based on the following information:
        
        Relevant Data:
        
        Stock price data: {{formatted_stock_data}}
        Industry share: {{stock_industry}}
        Today's date: {{time.strftime('%Y-%m-%d')}}
        Latest news summary: {{news_summary}}
        Latest K value: {{kd_value['K_value']}}
        Latest D value: {{kd_value['D_value']}}
        20-day average volume: (total shares traded over the last 20 days / 20)
        
        Tasks:
        
        1. Use the latest news summary as a reference to perform technical analysis for deriving final insights.
        2. Analyze the KD values as follows:
        - KD Golden Cross (K value breaking above D value): Buy point
        - KD Death Cross (K value breaking below D value): Sell point
        - KD value < 20 and daily volume > 20-day average volume: Buy point
        - KD value > 90 and daily volume < 20-day average volume: Sell point
        - KD value between 20 and 90 and daily volume > 20-day average volume: Continue to observe
        - KD value > 80 and daily volume > 20-day average volume: High-end oscillation
        - KD value < 20 and daily volume < 20-day average volume: Low-end oscillation
        
        3. Additionally, leverage the existing data to perform any relevant technical analysis (without introducing new variables), such as examining trend lines, support and resistance levels, or using insights from the latest news to contextualize the KD analysis.
        
        Response Format:
        
        1. Recent key news points: Provide the most significant items in English and their translations as needed.
        2. Next opening price prediction: e.g., 1xx.x (TWD).
        3. Next closing price prediction: e.g., 1xx.x (TWD).
        4. 9-day RSV calculation (Formula: (today's close - lowest in 9 days) / (highest in 9 days - lowest in 9 days) * 100).
        5. Analysis suggestions: Based on your technical analysis and current affairs, suggest actions such as 'buy', 'sell', 'hold', etc., and comment on future trends if not favorable.
    """
)
```

`news_summary` represents news data fetched via Python calling Bing News Search API.
`formatted_stock_data` includes stock price data from the last six months.
`stock_industry` refers to the percentage share of each company in the Taiwan ETF.
`kd_value` contains the K and D values obtained through Python scraping for the current and previous days.

---

🤝 **Let's Collaborate!**
If you have any questions or are interested in discussing this demo web application further, feel free to open an issue or contact us for a collaborative discussion. Your input and curiosity are what drive innovation and improvement!
