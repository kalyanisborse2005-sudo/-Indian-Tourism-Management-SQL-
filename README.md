# -Indian-Tourism-Management-SQL-
 A MySQL database project for organizing tourism data and exploring booking, payment, hotel, package, and destination trends across India. The SQL script creates the database schema, loads sample records, runs data checks, and demonstrates reporting queries
## Project contents

- `Indian Tourism Management.sql` — database creation, table definitions, sample data inserts, validation queries, and analytical SQL examples.

## Database schema

The project defines seven tables connected by primary and foreign keys:

| Table | Purpose |
|---|---|
| `Tourists` | Tourist profiles and home locations |
| `Destinations` | Indian destinations, regions, types, and entry fees |
| `Hotels` | Hotels, categories, room prices, and destination links |
| `Tour_Packages` | Packages, durations, prices, types, and destination links |
| `Bookings` | Tourist reservations, dates, group sizes, and status |
| `Payments` | Booking payments, dates, methods, and status |
| `Reviews` | Tourist ratings and written destination reviews |

## Requirements

- MySQL 8.0 or later
- A MySQL client such as MySQL Workbench or the `mysql` command-line client

The script uses `CREATE DATABASE`, `USE`, `LIMIT`, `YEAR()`, and `MONTHNAME()` syntax compatible with MySQL. It creates the database `Indian_Tourism_Management`.

## Run the project

1. Clone this repository:

   ```bash
   git clone https://github.com/<your-username>/<your-repository>.git
   cd <your-repository>
   ```

2. Run the SQL script from a terminal:

   ```bash
   mysql -u <your-mysql-user> -p < "Indian Tourism Management.sql"
   ```

   Or open `Indian Tourism Management.sql` in MySQL Workbench and execute it.

3. Refresh the schema list in your MySQL client and select `Indian_Tourism_Management` to inspect the tables and query results.

If the database already exists, inspect its contents before running the script again. The script does not drop or reset the database; repeated execution will encounter existing table names and primary keys.

## Included analysis

The script includes SQL examples for:

- Counting and checking loaded records
- Filtering bookings and completed payments
- Sorting and limiting payment results
- Joining bookings with tourist details
- Finding popular destinations and tour packages
- Summarizing booking status and monthly booking trends
- Identifying repeat tourists and monthly tourist demand
- Calculating destination review averages
- Comparing destination booking volume and ratings

## Notes

- The SQL file contains sample data for demonstration and learning; it is not a live booking system.
- Foreign keys link bookings to tourists, packages, and hotels; packages and hotels link to destinations; payments link to bookings; and reviews link tourists to destinations.
- Review the analytical query labeled **“Number of Tourists per Destination”** near the end of the script before using it. It joins `destinations.destination_id` to `bookings.package_id`, but the schema indicates that bookings should be associated with a destination through `bookings.package_id` → `tour_packages.package_id` → `tour_packages.destination_id`.
