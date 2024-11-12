# Redis-post-exloitation-tool
This script perform basic redis checks to perform post-exploitation

### How to Use the Script

1. **Save the Script**: Save the script to a file, for example, `redis_auto_exploiter.py`.

2. **Run the Script**: Execute the script with the target host and port as arguments.
   ```bash
   python redis_auto_exploiter.py <target_ip> <port>
   ```

   Example:
   ```bash
   python redis_auto_exploiter.py 192.168.1.100 6379
   ```

### Explanation

1. **Version Check**:
   - The script retrieves the Redis version using `r.info("server")` and checks if it is less than `7.0.12`, which is a known vulnerable version.

2. **Configuration Checks**:
   - **Bind Configuration**: Checks if the Redis server is configured to allow remote connections.
   - **Persistence Configuration**: Checks if the server has persistence enabled (RDB snapshots and AOF logging).

3. **Post-Exploitation Checks**:
   - **File Writing**: Attempts to write a PHP file to a web directory (`/var/www/html`) to test for arbitrary file write vulnerabilities. Adjust the directory as needed based on the target environment.

### **Permissions**: Ensure you have the necessary permissions to perform these actions on the target system!


### Additional Considerations

- **Logging**: You might want to add logging to record the results for further analysis.
- **Error Handling**: Enhance error handling to cover more edge cases.
- **Reporting**: Automate the generation of a report with detailed findings.
