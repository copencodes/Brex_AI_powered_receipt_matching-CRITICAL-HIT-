# Brex_AI_powered_receipt_matching-CRITICAL-HIT-
Team name: Critical Hit
# 🧾 AI Receipt Matching System

An advanced machine learning-powered system for automatically matching receipts to bank transactions with confidence scoring and intelligent decision making.

## ✨ Features

### Core Functionality
- **Smart Matching Algorithm**: Uses fuzzy string matching, amount analysis, date proximity, and currency validation
- **Confidence Scoring**: ML-based confidence calculation with customizable thresholds
- **Automated Decisions**: Three-tier decision system (Auto-Match, Review, Reject)
- **Real-time Processing**: Instant matching results with detailed feature breakdowns

### User Interface
- **Interactive Demo**: Test the system with sample data or custom inputs
- **Visual Results**: Color-coded confidence bars and detailed feature scores
- **Configuration Panel**: Adjust thresholds and parameters in real-time
- **Responsive Design**: Works seamlessly on desktop and mobile devices

### Multi-Currency Support
- USD, GBP, EUR, INR, JPY, CNY, RUB
- Currency matching as part of the context scoring

## 🚀 Quick Start

1. **Open the HTML file** in any modern web browser
2. **Run Full Demo** to see the system match all sample receipts to transactions
3. **Try Custom Matching** by entering your own receipt and transaction data
4. **Adjust Configuration** to see how different thresholds affect results

## 🎯 How It Works

### Matching Algorithm

The system evaluates four key features for each receipt-transaction pair:

1. **Vendor/Merchant Matching (45% weight)**
   - Fuzzy token-based string comparison
   - Handles variations in business names (e.g., "Starbucks" vs "Starbucks Coffee")

2. **Amount Matching (35% weight)**
   - Calculates relative deviation between amounts
   - Tolerates small differences (configurable threshold)

3. **Date Proximity (15% weight)**
   - Exponential decay function for date differences
   - Accounts for processing delays and weekend transactions

4. **Context Matching (5% weight)**
   - Currency validation
   - Additional contextual factors

### Confidence Calculation

Uses a sigmoid-based ML approach:
```
confidence = 1 / (1 + exp(-z))
where z = weighted_feature_sum * 4.0 - 2.0
```

### Decision Logic

| Confidence Score | Decision | Action |
|-----------------|----------|---------|
| ≥ Auto-Match Threshold (default 90%) | **Auto-Match** | Automatically approve |
| ≥ Review Threshold (default 70%) | **Review** | Flag for manual review |
| < Review Threshold | **Reject** | Automatically reject |

### Guardrails

Safety mechanisms prevent incorrect matches:
- Maximum date difference (default: 14 days)
- Maximum amount deviation (default: 10%)
- Currency mismatch detection

## ⚙️ Configuration Options

### Thresholds
- **Auto-Match Threshold**: Minimum confidence for automatic approval (0.0-1.0)
- **Review Threshold**: Minimum confidence for manual review (0.0-1.0)

### Constraints
- **Max Date Difference**: Maximum days between receipt and transaction (1-30)
- **Max Amount Deviation**: Maximum percentage difference in amounts (0-50%)

## 📊 Sample Data

### Receipts
The system includes 10 sample receipts from various vendors:
- Coffee shops (Starbucks, Caffè Nero)
- Transportation (Uber, Delta Air Lines)
- Food delivery (DoorDash)
- Tech services (Scale AI, Coinbase)
- Retail (Allbirds, SeatGeek)

### Transactions
Corresponding bank transactions with slight variations:
- Different merchant name formats
- Small amount differences
- Date processing delays
- Currency variations

## 🎨 User Interface Components

### Results Display
- **Color-coded confidence bars**: Green (auto-match), Yellow (review), Red (reject)
- **Feature breakdown**: Individual scores for each matching component
- **Decision reasoning**: Explanation of why each decision was made

### Interactive Controls
- **Custom input forms**: Test your own receipt/transaction pairs
- **Random sampling**: Generate test cases automatically
- **Real-time configuration**: Adjust parameters and see immediate effects

## 🔧 Technical Details

### Architecture
- **Frontend**: Pure HTML/CSS/JavaScript (no external dependencies)
- **Algorithms**: Custom fuzzy matching, sigmoid confidence scoring
- **Data Storage**: In-memory (no backend required)

### Browser Compatibility
- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

### Performance
- Instant matching for single pairs
- Sub-second processing for full dataset (10+ receipts)
- Responsive UI with smooth animations

## 🎮 Usage Examples

### Basic Matching
1. Enter receipt details: "Starbucks", $4.50, "2025-08-12"
2. Enter transaction details: "Starbucks Coffee", $4.50, "2025-08-12"
3. Click "Match Custom Pair"
4. Result: 95%+ confidence, Auto-Match decision

### Edge Cases
1. **Date Mismatch**: Receipt on Friday, transaction on Monday
   - Still matches due to weekend processing delays
2. **Name Variations**: "McDonald's" vs "McDonald's Restaurant"
   - Fuzzy matching handles common variations
3. **Small Amount Differences**: Receipt $10.00, transaction $10.05
   - Tolerates small processing fees or rounding

## 🔍 Troubleshooting

### Low Confidence Scores
- Check vendor/merchant name similarity
- Verify amount differences are within tolerance
- Ensure dates are reasonably close
- Confirm currency matching

### Unexpected Decisions
- Review threshold settings in configuration
- Check if guardrails are being triggered
- Examine individual feature scores

### Performance Issues
- Refresh page to reset state
- Check browser console for errors
- Ensure JavaScript is enabled

## 📈 Future Enhancements

- **Machine Learning**: Train on real transaction data
- **Advanced NLP**: Better vendor name matching with semantic understanding
- **Batch Processing**: Handle large datasets efficiently
- **API Integration**: Connect to banking and receipt scanning services
- **Analytics Dashboard**: Track matching accuracy and performance metrics

## 🤝 Contributing

This is a demonstration system showcasing AI-powered receipt matching concepts. For production use, consider:

1. **Data Security**: Implement proper encryption and data handling
2. **Scale Testing**: Validate performance with larger datasets
3. **ML Training**: Use real transaction data to improve accuracy
4. **Error Handling**: Add comprehensive error handling and logging
5. **Testing**: Implement unit and integration tests

## 📝 License

This project is for demonstration purposes. Feel free to use and modify for educational or commercial applications.

---

**Built with ❤️ to showcase the power of AI in financial automation**
