package main

import ( "fmt","log","os" )

)

func main() {
 // Get environment variables
 dbHost := os.Getenv("DB_HOST")
 dbPort := os.Getenv("DB_PORT")
 dbUser := os.Getenv("DB_USER")
 dbPassword := os.Getenv("DB_PASSWORD")
 appName := os.Getenv("APP_NAME")

 // Check if all required environment variables are set
 if dbHost == "" || dbPort == "" || dbUser == "" || dbPassword == "" || appName == "" {
  log.Fatal("Error: Missing required environment variables.")
 }

 // Print the environment variables
 fmt.Println("Environment Variables:")
 fmt.Printf("DB_HOST: %s\n", dbHost)
 fmt.Printf("DB_PORT: %s\n", dbPort)
 fmt.Printf("DB_USER: %s\n", dbUser)
 fmt.Printf("DB_PASSWORD: %s\n", dbPassword)
 fmt.Printf("APP_NAME: %s\n", appName)

 // ... Use the environment variables in your application logic ...
}


   import (
       "database/sql"
       _ "github.com/lib/pq" // PostgreSQL driver
   )

   func main() {
       // Get environment variables 

       // Create a database connection using the environment variables
       db, err := sql.Open("postgres", fmt.Sprintf("host=%s port=%s user=%s password=%s dbname=mydatabase", dbHost, dbPort, dbUser, dbPassword))
       if err != nil {
           log.Fatal(err)
       }
       defer db.Close()

       // Use the database connection 
   }
   
   import (
       "net/http"
   )

   func main() {
       // Get environment variables

       // Define the API endpoint using the environment variable
       apiEndpoint := fmt.Sprintf("https://api.example.com/%s", appName)

       // Make an HTTP request to the API endpoint
       resp, err := http.Get(apiEndpoint)
       if err != nil {
           log.Fatal(err)
       }
       defer resp.Body.Close()

       // Process the response 
   }
   
