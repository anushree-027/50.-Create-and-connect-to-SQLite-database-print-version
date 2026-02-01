# 50.-Create-and-connect-to-SQLite-database-print-version
import sqlite3

try:
    sqlite_connection = sqlite3.connect('temp.db')
    cursor = sqlite_connection.cursor()

    print("Database created and connected to SQLite.")

    cursor.execute("select sqlite_version();")
    record = cursor.fetchall()

    print("SQLite Database Version is:", record)

except sqlite3.Error as error:
    print("Error while connecting to SQLite:", error)

finally:
    if sqlite_connection:
        sqlite_connection.close()
        print("The SQLite connection is closed.")
