# ADHD-QUOTES
ADHD QUOTES
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ADHD Affirmations Widget</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: transparent;
    }

    .widget {
      width: 100%;
      max-width: 420px;
      min-height: 250px;
      padding: 22px;
      border-radius: 24px;
      background: linear-gradient(180deg, #fffaf7 0%, #f8f1ee 100%);
      border: 1px solid #eadfda;
      box-shadow: 0 10px 30px rgba(120, 90, 90, 0.08);
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 16px;
    }

    .label {
      display: inline-block;
      width: fit-content;
      padding: 6px 12px;
      border-radius: 999px;
      background: #f3e3df;
      color: #8b6f6a;
      font-size: 12px;
      font-weight: 600;
      letter-spacing: 0.02em;
    }

    .quote {
      font-size: 22px;
      line-height: 1.45;
      color: #463a37;
      font-weight: 600;
      margin: 0;
    }

    .subtext {
      font-size: 14px;
      line-height: 1.6;
      color: #8c7a76;
      margin-top: 6px;
    }

    .footer {
      display: flex;
      justify-content: space-between;
      gap: 10px;
      flex-wrap: wrap;
      align-items: center;
    }

    .counter {
      font-size: 12px;
      color: #9c8a86;
    }

    button {
      border: none;
      border-radius: 14px;
      padding: 10px 14px;
      font-size: 13px;
      font-weight: 600;
      cursor: pointer;
      transition: 0.2s ease;
    }

    .new-btn {
      background: #d8b9b0;
      color: white;
    }

    .new-btn:hover {
      opacity: 0.92;
      transform: translateY(-1px);
    }

    .copy-btn {
      background: #efe5e1;
      color: #7e6964;
    }

    .copy-btn:hover {
      background: #e8dbd5;
    }

    @media (max-width: 480px) {
      .widget {
        min-height: 220px;
        padding: 18px;
      }

      .quote {
        font-size: 19px;
      }
    }
  </style>
</head>
<body>
  <div class="widget">
    <div>
      <span class="label">ADHD Affirmation</span>
      <p class="quote" id="quote">You do not need to do everything at once.</p>
      <p class="subtext" id="subtext">One small step still counts as progress.</p>
    </div>

    <div class="footer">
      <span class="counter" id="counter">1 / 16</span>
      <div style="display:flex; gap:8px;">
        <button class="copy-btn" onclick="copyQuote()">Copy</button>
        <button class="new-btn" onclick="nextQuote()">New quote</button>
      </div>
    </div>
  </div>

  <script>
    const quotes = [
      {
        quote: "You do not need to do everything at once.",
        subtext: "One small step still counts as progress."
      },
      {
        quote: "Your pace is valid.",
        subtext: "Slow progress is still real progress."
      },
      {
        quote: "You are not lazy.",
        subtext: "You may just need rest, clarity, or a gentler starting point."
      },
      {
        quote: "Done is powerful, even when it is imperfect.",
        subtext: "Perfection is not required for progress."
      },
      {
        quote: "It is okay to begin with the easiest thing.",
        subtext: "Starting small often creates momentum."
      },
      {
        quote: "Your brain works differently, not wrongly.",
        subtext: "You deserve tools and systems that support you."
      },
      {
        quote: "You can reset at any moment.",
        subtext: "This day is not ruined just because it feels messy."
      },
      {
        quote: "You are allowed to need reminders.",
        subtext: "Support does not make you less capable."
      },
      {
        quote: "Focus is not a moral achievement.",
        subtext: "Struggling to focus does not define your worth."
      },
      {
        quote: "Small effort is still effort.",
        subtext: "Celebrate what you did, not only what is left."
      },
      {
        quote: "You are not behind.",
        subtext: "You are moving through life in your own way."
      },
      {
        quote: "Rest is productive when your brain is overloaded.",
        subtext: "Pausing can help you return with more clarity."
      },
      {
        quote: "One task at a time is enough.",
        subtext: "You do not need to hold the entire day in your head."
      },
      {
        quote: "You are allowed to make things easier.",
        subtext: "Ease is not cheating."
      },
      {
        quote: "Your value is not measured by consistency alone.",
        subtext: "You are still worthy on low-energy days."
      },
      {
        quote: "Today only needs one next step.",
        subtext: "Start there."
      }
    ];

    let currentIndex = 0;

    function renderQuote() {
      document.getElementById("quote").textContent = quotes[currentIndex].quote;
      document.getElementById("subtext").textContent = quotes[currentIndex].subtext;
      document.getElementById("counter").textContent = `${currentIndex + 1} / ${quotes.length}`;
    }

    function nextQuote() {
      let newIndex;
      do {
        newIndex = Math.floor(Math.random() * quotes.length);
      } while (newIndex === currentIndex && quotes.length > 1);
      currentIndex = newIndex;
      renderQuote();
    }

    function copyQuote() {
      const text = `${quotes[currentIndex].quote} ${quotes[currentIndex].subtext}`;
      navigator.clipboard.writeText(text);
    }

    renderQuote();
  </script>
</body>
</html>
