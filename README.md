# Invoice Management System

A comprehensive billing and invoice management software built with React.js frontend and Node.js/Express backend.

## Features

### Core Functionality
- **Product Management**: Add, edit, delete products with SKU, pricing, and inventory tracking
- **Customer Management**: Maintain customer database with contact details and GST information
- **Invoice Generation**: Create professional invoices with automatic numbering
- **PDF Export**: Download invoices as PDF documents
- **Invoice Search**: Search invoices by number, customer, date, or product
- **Payment Tracking**: Track payment status (Paid/Unpaid/Partial)

### Dashboard & Analytics
- **Sales Dashboard**: Overview of total sales, invoices, customers, and products
- **Visual Charts**: Monthly sales trends and top-selling products
- **Reports**: Generate detailed sales reports with date filtering
- **Export Options**: Export reports as PDF or Excel files

### Advanced Features
- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Real-time Updates**: Live data synchronization
- **Invoice Email**: Send invoices directly to customers
- **Multi-currency Support**: Handle different currencies
- **Tax Management**: Configurable tax rates and GST support
- **Discount Management**: Apply discounts to invoices

## Technology Stack

### Frontend
- **React.js** - Modern UI framework
- **React Router** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **Recharts** - Data visualization
- **jsPDF** - PDF generation
- **Axios** - HTTP client

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **Nodemailer** - Email sending

## Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud)
- npm or yarn

### Backend Setup
1. Navigate to server directory:
   ```bash
   cd server
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create environment file:
   ```bash
   cp .env.example .env
   ```

4. Update `.env` with your configuration:
   ```
   MONGODB_URI=mongodb://localhost:27017/invoice_management
   PORT=5000
   JWT_SECRET=your_secret_key
   ```

5. Start the server:
   ```bash
   npm run dev
   ```

### Frontend Setup
1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the development server:
   ```bash
   npm run dev
   ```

3. Open browser and navigate to `http://localhost:3000`

## Database Schema

### Products
- name, sku, price, category, stock, description
- Automatic inventory tracking

### Customers
- name, email, phone, address, gstNumber
- Unique email validation

### Invoices
- invoiceNumber (auto-generated), customerId, date, dueDate
- items[], subtotal, tax, discount, total, status, notes
- Automatic calculations

## API Endpoints

### Products
- `GET /api/products` - Get all products
- `POST /api/products` - Create product
- `PUT /api/products/:id` - Update product
- `DELETE /api/products/:id` - Delete product

### Customers
- `GET /api/customers` - Get all customers
- `POST /api/customers` - Create customer
- `PUT /api/customers/:id` - Update customer
- `DELETE /api/customers/:id` - Delete customer

### Invoices
- `GET /api/invoices` - Get all invoices
- `POST /api/invoices` - Create invoice
- `PUT /api/invoices/:id` - Update invoice
- `DELETE /api/invoices/:id` - Delete invoice
- `POST /api/invoices/:id/send-email` - Email invoice

### Dashboard & Reports
- `GET /api/dashboard/stats` - Dashboard statistics
- `GET /api/dashboard/sales-chart` - Sales chart data
- `GET /api/reports` - Generate reports
- `GET /api/reports/export/pdf` - Export PDF report
- `GET /api/reports/export/excel` - Export Excel report

## Usage Guide

### Creating Products
1. Navigate to Products page
2. Click "Add Product" button
3. Fill in product details (name, SKU, price, category, stock)
4. Save the product

### Managing Customers
1. Go to Customers page
2. Add customer information including GST number
3. Customers can be edited or deleted as needed

### Generating Invoices
1. Click "Create Invoice" from Invoices page
2. Select customer from dropdown
3. Add products to invoice with quantities
4. Set tax rate and apply discounts if needed
5. Save invoice - PDF can be downloaded immediately

### Viewing Reports
1. Access Reports page for analytics
2. Filter by date range
3. View charts for sales trends and top products
4. Export reports as PDF or Excel

## Customization

### Adding New Fields
- Update database models in `server/models/`
- Modify API routes in `server/routes/`
- Update frontend forms and components

### Styling Changes
- Modify Tailwind classes in components
- Update `tailwind.config.js` for theme changes
- Add custom CSS in `src/index.css`

### Email Templates
- Customize email templates in server routes
- Configure SMTP settings in `.env`

## Deployment

### Frontend (Netlify/Vercel)
1. Build the project: `npm run build`
2. Deploy the `dist` folder

### Backend (Heroku/Railway)
1. Set environment variables
2. Deploy server directory
3. Ensure MongoDB connection

### Database (MongoDB Atlas)
1. Create cluster on MongoDB Atlas
2. Update connection string in `.env`
3. Configure network access

## Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -am 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Submit pull request

## License

This project is licensed under the MIT License.

## Support

For support and questions:
- Create an issue on GitHub
- Email: support@invoicemanagement.com

## Roadmap

- [ ] Multi-user support with roles
- [ ] Barcode scanning integration
- [ ] Mobile app development
- [ ] Advanced reporting features
- [ ] Integration with payment gateways
- [ ] Multi-language support
- [ ] Automated backup system