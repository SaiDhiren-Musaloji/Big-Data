# Flight Data Analysis using MapReduce and Oozie

## Project Description
This project implements an Oozie-based workflow that orchestrates three MapReduce programs to analyze flight data efficiently. The analysis addresses the following key questions:
1. **On-Time Flights**: Identifying airlines with the highest and lowest probabilities of being on schedule.
2. **Average Taxi Time**: Determining airports with the longest and shortest average taxi times per flight (both in and out).
3. **Flight Cancellations**: Analyzing the most common reasons for flight cancellations.

The workflow is optimized for distributed computation using Hadoop, with performance tuning across varying computational resources and data sizes.

---

## Repository Structure
```
map-reduce/
├── job.properties
├── workflow.xml
├── command.txt
├── flight.java
├── output.txt
└── Report.pdf
```

### File Descriptions:
- **map-reduce/**: Contains configuration and scripts to run the Oozie workflow.
  - `job.properties`: Configuration file for the Oozie workflow.
  - `workflow.xml`: Defines the workflow structure in Oozie.
- **command.txt**: Instructions for executing the MapReduce programs.
- **flight.java**: Java implementation of the MapReduce jobs.
- **output.txt**: Sample output of the analysis.
- **Report.pdf**: A detailed report describing the project, methodology, and results.

---

## Key Features
### A. On-Time Flights
- Calculates the probability of each airline being on schedule.
- Ranks airlines based on their punctuality.

### B. Average Taxi Time
- Computes average taxi times for each airport.
- Highlights the best and worst-performing airports based on taxi time.

### C. Flight Cancellations
- Identifies and ranks the most frequent reasons for flight cancellations.

---

## Performance Analysis
1. **Scalability with Virtual Machines (VMs)**:
   - Execution time decreases significantly as the number of VMs increases, demonstrating efficient parallel processing.
   - Example: A reduction from 850 seconds with 2 VMs to 301 seconds with 7 VMs.
   
2. **Data Size Impact**:
   - Execution time increases with larger datasets, as expected.
   - Example: From 68 seconds for one year of data to 301 seconds for 22 years.

Performance plots are available in the `Report.pdf`.

---

## Execution Instructions
1. Upload the MapReduce JAR (`flight.java`) and dataset to the Hadoop cluster.
2. Configure the Oozie workflow using `job.properties` and `workflow.xml`.
3. Run the workflow using the following command:
   ```bash
   oozie job -oozie http://<oozie-server>:11000/oozie -config job.properties -run
   ```
4. Check output logs for results.

---

## Technologies Used
- **Hadoop MapReduce**: For parallel data processing.
- **Apache Oozie**: For workflow orchestration.
- **Java**: For implementing MapReduce logic.
- **Python (Optional)**: Utility scripts and bin.py.
- **High-Performance Computing (HPC)**: Leveraging distributed clusters for execution.
