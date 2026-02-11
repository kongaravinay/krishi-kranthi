# KRISHI KRANTHI - Agricultural E-Commerce Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Flask 2.0+](https://img.shields.io/badge/Flask-2.0+-red.svg)](https://flask.palletsprojects.com/)
[![MySQL 8.0+](https://img.shields.io/badge/MySQL-8.0+-blue.svg)](https://www.mysql.com/)

A web platform connecting farmers directly with consumers, eliminating middlemen from agricultural trade.

## What's the problem?

Indian farmers typically only get 25-40% of the retail price because multiple intermediaries take cuts along the supply chain. A farmer might sell to a local agent, who sells to a wholesaler, who sells to a distributor, who finally sells to a retailer. By the time produce reaches consumers, prices are inflated and farmers have been squeezed.

## How does KRISHI KRANTHI help?

This platform lets farmers:
- List their crops directly
- Set their own prices
- Sell straight to consumers
- Track orders in real-time
- Get information about government support programs

And gives consumers:
- Direct access to fresh farm produce
- Fair prices without markup from middlemen
- Full traceability back to the farmer
- Transparent pricing information

## Key Features

**Farmer Features:**
- Register and manage farm profile
- List multiple crops with details (season, quantity, price)
- Update or remove product listings
- Track customer orders
- View government agricultural schemes

**Consumer Features:**
- Browse products with search and filter
- Add items to cart
- Checkout and get order confirmation
- See all product details including farmer location
- Fair pricing without hidden charges

**Admin Features:**
- Manage all users (farmers and consumers)
- Monitor transactions
- Manage government schemes database
- System-wide analytics

## Technology Stack

**Backend:**
- Python 3.9+
- Flask 2.x
- MySQL 8.0+
- PyMySQL for database connection

**Frontend:**
- HTML5
- CSS3
- Bootstrap 5
- JavaScript (vanilla)

**Tools:**
- Git for version control
- XAMPP for local development

## Project Structure

```
krishi-kranthi/
├── app/
│   ├── main.py                 # Flask app entry point
│   ├── models.py               # Database models
│   ├── routes/
│   │   ├── auth.py             # Login, register
│   │   ├── farmer.py           # Farmer dashboard
│   │   ├── consumer.py         # Consumer marketplace
│   │   └── admin.py            # Admin panel
│   ├── static/
│   │   ├── css/                # Stylesheets
│   │   ├── js/                 # JavaScript files
│   │   └── images/             # UI images
│   └── templates/
│       ├── base.html           # Base template
│       ├── index.html          # Home page
│       ├── farmer/             # Farmer pages
│       ├── consumer/           # Consumer pages
│       └── admin/              # Admin pages
├── database/
│   ├── schema.sql              # Database tables
│   └── seed_data.sql           # Sample data
├── docs/
│   ├── API.md                  # API reference
│   ├── DATABASE.md             # Database design
│   ├── SETUP.md                # Setup instructions
│   └── DEPLOYMENT.md           # Production deployment
├── tests/
│   ├── test_auth.py
│   ├── test_products.py
│   └── test_orders.py
├── config/
│   ├── config.py               # App configuration
│   └── .env.example            # Environment template
├── scripts/
│   ├── setup_db.py             # Database setup
│   └── seed_db.py              # Load sample data
├── requirements.txt
├── README.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
└── LICENSE
```

## Getting Started

### Prerequisites
- Python 3.9 or later
- MySQL 8.0 or later
- Git
- pip

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/krishi-kranthi.git
cd krishi-kranthi
```

2. Create virtual environment:
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up environment variables:
```bash
cp config/.env.example config/.env
# Edit config/.env with your database credentials
```

5. Create and seed database:
```bash
# Run from command line
mysql -u root -p < database/schema.sql
mysql -u root -p krishikranthi < database/seed_data.sql

# Or use Python script
python scripts/setup_db.py
python scripts/seed_db.py
```

6. Run the application:
```bash
python app/main.py
```

Visit `http://localhost:5000` in your browser.

## Configuration

Edit `config/.env` with your settings:

```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=krishikranthi
DB_PORT=3306

FLASK_ENV=development
FLASK_DEBUG=True
SECRET_KEY=your_secret_key_here

SERVER_HOST=0.0.0.0
SERVER_PORT=5000
```

## How to Use

### As a Farmer

1. Go to home page and click "Register as Farmer"
2. Fill in your farm details (name, location, contact)
3. Login with your mobile number and password
4. Click "Add Product" to list your crops
5. Fill in crop details (name, quantity, price, season)
6. Monitor orders from your dashboard
7. View available government schemes

### As a Consumer

1. Go to home page and click "Register as Consumer"
2. Fill in your details
3. Login with your email and password
4. Browse available products
5. Use search or filters to find specific crops
6. Add items to cart
7. Review and confirm your order
8. Get order confirmation with receipt

## Database Schema

Main tables:
- **farmers**: Stores farmer information
- **consumers**: Stores consumer information  
- **products**: Farm products listed by farmers
- **orders**: Customer orders
- **orderitems**: Individual items in orders
- **govtschemes**: Government support programs

See `docs/DATABASE.md` for complete ER diagram and relationships.

## API Endpoints

### Authentication
- `POST /auth/farmer/register` - Farmer registration
- `POST /auth/farmer/login` - Farmer login
- `POST /auth/consumer/register` - Consumer registration
- `POST /auth/consumer/login` - Consumer login
- `GET /auth/logout` - Logout

### Products
- `GET /products` - List all products
- `POST /products` - Add new product (farmer only)
- `PUT /products/<id>` - Update product (farmer only)
- `DELETE /products/<id>` - Delete product (farmer only)

### Orders
- `POST /cart/add/<product_id>` - Add to cart
- `POST /checkout` - Place order
- `GET /orders` - View user orders

See `docs/API.md` for complete API documentation.

## Testing

Run tests with:
```bash
pytest
```

Run specific test file:
```bash
pytest tests/test_auth.py -v
```

With coverage:
```bash
pytest --cov=app tests/
```

## Future Enhancements

- Payment gateway integration (Razorpay, UPI)
- Real-time order notifications
- Mobile app (iOS/Android)
- Price prediction using machine learning
- Multi-language support (Hindi, Kannada, Telugu, Tamil)
- Weather and soil data integration
- Logistics tracking
- Rating and review system

## Contributing

We'd love your contributions! Please check out [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

Quick steps:
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Make your changes
4. Write or update tests if needed
5. Commit: `git commit -m 'Add some feature'`
6. Push: `git push origin feature/your-feature-name`
7. Open a Pull Request

## Project Background

This project was developed as part of a Bachelor's degree program in Computer Science at GITAM School of Technology. The goal was to create a practical solution to a real problem: how to help farmers get fair prices for their produce.

The platform was built and tested with real farmer data from Karnataka region, validating that the concept works in practice.

## Known Issues

- Payment integration not yet implemented (cash/bank transfer only)
- Mobile responsiveness could be improved
- Admin dashboard analytics are basic
- No real-time notifications yet

## References

- Flask: https://flask.palletsprojects.com/
- MySQL: https://www.mysql.com/
- Bootstrap: https://getbootstrap.com/
- Government Schemes: https://farmer.gov.in/
- NITI Aayog Report on Doubling Farmers Income

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Contact

Questions or suggestions?
- LinkedIn: https://www.linkedin.com/in/nagavinay-kongara/
- GitHub: https://github.com/kongaravinay

## Acknowledgments

This project was guided by Dr. Monica Jha from GITAM School of Technology. Thanks to all the farmers who provided real-world data and feedback.

---

Last Updated: February 2026
