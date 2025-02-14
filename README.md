# Banking System

A robust C++ banking system application with MySQL database integration that provides essential banking operations through a command-line interface.

## Features

- **Account Management**
  - Create new bank accounts (Savings/Current)
  - Generate unique account numbers automatically
  - Store account holder details securely

- **Transaction Operations**
  - Deposit funds
  - Withdraw funds with balance validation
  - Check account balance
  - View all accounts in the system

- **Security Features**
  - Input validation for all operations
  - Error handling for database operations
  - Protection against negative balance transactions

## Technical Stack

- **Language:** C++
- **Database:** MySQL
- **Libraries Required:**
  - `mysql_driver.h`
  - `mysql_connection.h`
  - `cppconn/prepared_statement.h`
  - `cppconn/resultset.h`

## Prerequisites

1. C++ compiler (supporting C++11 or later)
2. MySQL Server installed and running
3. MySQL Connector/C++ library
4. MySQL development libraries

## Database Setup

1. Create a new MySQL database named `banking_system`
2. Create the accounts table using the following SQL:

```sql
CREATE TABLE accounts (
    accountNum BIGINT PRIMARY KEY,
    accountHolder VARCHAR(255),
    accBalance BIGINT,
    accountType VARCHAR(50)
);
```

## Configuration

Update the database connection details in the `Bank` constructor:
```cpp
con = driver->connect("tcp://127.0.0.1:3306", "root", "YOUR_PASSWORD");
```

## Features Implementation

### Account Class
- Manages individual account details
- Generates random account numbers
- Handles account holder information
- Maintains account balance and type

### Bank Class
- Handles all banking operations
- Manages database connections
- Implements CRUD operations
- Provides transaction functionality

## Usage

1. **Create Account**
   - Enter account holder name
   - Choose account type (S for Savings/C for Current)
   - Provide initial deposit amount

2. **Deposit Money**
   - Enter account number
   - Specify deposit amount

3. **Withdraw Money**
   - Enter account number
   - Specify withdrawal amount
   - System validates sufficient balance

4. **Check Account Details**
   - Enter account number to view complete account information

5. **View All Accounts**
   - Displays a list of all accounts with their balances

## Error Handling

The system includes comprehensive error handling for:
- Invalid input values
- Database connection failures
- Insufficient balance scenarios
- Invalid account numbers
- Transaction failures

## Security Considerations

- Input validation for all user inputs
- Prepared statements for SQL queries to prevent SQL injection
- Transaction amount validation
- Balance verification before withdrawals

## Future Improvements

1. Add transaction history logging
2. Implement user authentication
3. Add support for different currency types
4. Include interest calculation for savings accounts
5. Add support for account deletion

## Contributing

Feel free to fork this project and submit pull requests for any improvements.

## License

This project is open source and available under the MIT License.
