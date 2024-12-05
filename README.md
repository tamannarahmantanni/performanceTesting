Performance Testing

This repository contains performance testing files for two tasks using JMeter. The goal is to test the performance of the **Restful Booker API** and the **dmoney API** under different conditions and scenarios.

## Task 1: Performance Testing for Restful Booker API

### Objective
Perform load and stress testing for the following operations:
1. Login
2. Create Booking
3. Search

#### Load Testing Steps
1. Use a Gaussian Random Timer:
   - Deviation: 2000ms
   - Constant Delay: 500ms
2. Test Phases:
   - Step 1: 5-minute load test
   - Step 2: 10-minute load test
   - Step 3: 20-minute load test
3. Generate a load test report, including throughput and server capacity insights.

#### Stress Testing Steps
- Gradually increase the number of users until the server fails to handle the load.
- Identify bottlenecks and report the maximum sustainable throughput.

### Deliverables for Task 1
- Successful load test(20 minute) : https://drive.google.com/file/d/1GbV9L1QxvinJ_YiXR2ezvx-NOdQLdGie/view?usp=sharing
- Report for load test : https://docs.google.com/spreadsheets/d/1XqHf2-vTCAdXf7up3pNxs-4CKGKLP2GQ/edit?usp=sharing&ouid=113434615955561700751&rtpof=true&sd=true
- Stress test with bottleneck : https://drive.google.com/file/d/1O5dwkFEL6XjzGgcYlOMgOB3tRLbnuKjp/view?usp=sharing
- Report for stress test : https://docs.google.com/spreadsheets/d/1j2C2jha3V176fSNTFhBx-NPoc7y4gFd5/edit?usp=sharing&ouid=113434615955561700751&rtpof=true&sd=true



Task 2: Scenario-Based Testing for dmoney API

### Objective
Simulate transactions involving agents, customers, and merchants, ensuring the API functions as expected under the described scenario.

### Scenario Details
1. **Agents**: 5 agents perform deposits for 10 customers.
2. **Customers**: 5 customers send money to another 10 customers.
3. **Merchants**: 5 customers make payments to 2 merchants.

#### Key Configurations
- Generate an admin token for authentication.
- Use three threads for each transaction type with a **120-second ramp-up time**.
- Randomize transaction amounts with the Random Variable Controller.
- Include assertions to validate transaction success.

### Deliverables for Task 2
- Picture of request summary and html report : https://drive.google.com/file/d/1oPcQlwgC2GaF6qwlSUnwvJ1xVV5QgqiJ/view?usp=sharing




## Prerequisites
1. Install [JMeter](https://jmeter.apache.org/download_jmeter.cgi).
2. Ensure the required APIs are accessible:
   - [Restful Booker API](https://restful-booker.herokuapp.com/)
   - dmoney API

---

## How to Run the Tests

### Task 1: Running `booking.jmx`
1. Open **`booking.jmx`** in JMeter.
2. Configure the thread group for load and stress testing.
3. Add the Gaussian Random Timer as specified.
4. Execute the test and generate the HTML report.
5. Save the results in **`booking-api-test-report.xlsx`**.

### Task 2: Running `dmoney.jmx`
1. Open **`dmoney.jmx`** in JMeter.
2. Load the CSV files (`deposit.csv`, `sendMoney.csv`, `payment.csv`).
3. Set the thread group as per the scenario.
4. Execute the test and save the HTML report.
