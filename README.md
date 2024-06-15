The Order Processing Application is designed to process customer orders from a CSV file,
create users and orders via gRPC calls to respective services, and store processed orders in a JSON file.

Features:

CSV File Processing: Reads customer order details from a CSV file.
User Service: Creates users using customer information.
Order Service: Creates orders using customer and user information.
JSON File Output: Stores processed orders in a JSON file.

Technologies Used:

Java
Spring Boot
Spring Batch
gRPC
Lombok (for auto-generated getters, setters, and constructors)
Protobuf (for defining gRPC services)
Prerequisites
Java 17
Maven installed
Docker
Postgress
MongoDB
IDE (like IntelliJ IDEA or Eclipse) with Lombok plugin installed (if using IntelliJ IDEA, install Lombok plugin and enable annotation processing)
Setup

Clone the repository:

bash
Copy code
git clone https://github.com/jeena1995/ohs-api-test/ohs-api-test.zip.git
cd order-processing-app

Build the project:
mvn clean install

Configure Application Properties:

Open src/main/resources/application.properties.

Configure the following properties according to your environment:

# gRPC server addresses
grpc.order-service.host=localhost
grpc.order-service.port=50053

grpc.user-service.host=localhost
grpc.user-service.port=50054

# Input CSV file path
input.file=classpath:order-integration.csv

# Output JSON file path
output.file=processed-orders.json

Run the Application:

mvn spring-boot:run
This command starts the Spring Boot application. It will read data from the specified CSV file, process orders, and write the processed orders to a JSON file.

Verify Output:

Once the application completes processing:
Check the processed-orders.json file in the project directory for the processed orders.

Troubleshooting:
CSV Parsing Issues: Ensure the CSV file is correctly formatted and matches the expected structure defined in the Customer model.
gRPC Connection Issues: Verify that the gRPC server for both OrderService and UserService is running and accessible at the configured host and port.
File Path Issues: Ensure the paths specified in application.properties for input and output files are correct and accessible.
Additional Notes
This application assumes you have the necessary gRPC services (OrderService and UserService) running locally on the specified ports.

Issues :
I was facing issues with the connection, so I could not verify the end to end process because of the time limit.
