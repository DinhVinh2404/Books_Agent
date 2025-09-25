<div align="center">
<h2>Book Agent</h2>
</div>

## Abstract
Create an AI Agent that can look up book information and support book ordering.

## Database Schema

The application uses a SQLite database with the following two tables:

### Books Table
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| book_id     | INTEGER   | Primary key, unique ID for each book |
| title       | TEXT      | Title of the book |
| author      | TEXT      | Author of the book |
| price       | REAL      | Price of the book |
| stock       | INTEGER   | Number of books available in stock |
| category    | TEXT      | Category of the book |

**Example rows:**
| book_id | title        | author | price  | stock | category |
|---------|-------------|--------|--------|-------|----------|
| 1       | Chatbot      | Vinh   | 24.04  | 1     | Test     |
| 2       | User manual  | Vinh2  | 2003.0 | 5     | Manual   |

---

### Orders Table
| Column Name    | Data Type | Description |
|----------------|-----------|-------------|
| order_id       | INTEGER   | Primary key, unique ID for each order |
| customer_name  | TEXT      | Name of the customer placing the order |
| phone          | TEXT      | Customer phone number |
| address        | TEXT      | Customer shipping address |
| book_id        | INTEGER   | Foreign key referencing `Books.book_id` |
| quantity       | INTEGER   | Number of copies ordered |
| status         | TEXT      | Status of the order (e.g., Pending) |

**Example rows:**
| order_id | customer_name | phone      | address | book_id | quantity | status |
|----------|---------------|-----------|--------|---------|---------|--------|
| 1        | VinhDV        | 012345678 | Hanoi  | 1       | 1       | Pending |
