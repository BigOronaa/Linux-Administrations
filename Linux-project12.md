#  Process Management

---

## Objective  
I learned how to manage processes in Linux, including starting, stopping, and monitoring processes.  

---

## Steps I Took  

### 1. Start a Background Process  
I started a long-running process in the background using:  

```bash
sleep 300 &
```

Output:  
```
[1] 100404
```

### I added Screenshots
![alt text](images5/sleep.png)

---

### 2. List Running Processes  
I listed all running processes with:  

```bash
ps aux
```

This showed me the running `sleep` process along with other system processes.  

### I added Screenshots
![alt text](images5/ps.png)

---

### 3. Kill a Process  
I found the process ID (PID) of the sleep process and killed it using:  

```bash
kill 100404
```

### I added Screenshots
![alt text](images5/ps-aux.png)

---

### 4. Monitor System Resources  
I monitored system resources with:  

```bash
top
```

This displayed CPU, memory usage, and real-time process monitoring.  

### I added Screenshots
![alt text](images5/top.png

---

### 5. Change Process Priority  
I started a new sleep process with a lower priority using:  

```bash
nice -n 10 sleep 300 &
```

Output:  
```
[2] 100682
```

Then, I changed its priority using:  

```bash
sudo renice -n 5 -p 100682
```

Output:  
```
100682 (process ID) priority changed to 5
```

### I added Screenshots
![alt text](images5/nice.png)

---

## Conclusion  
Through this project, I practiced:  
- Starting and stopping processes.  
- Monitoring system activity with `top`.  
- Managing process priorities using `nice` and `renice`.  

I now have a solid understanding of **Linux process management** and how to control system resources effectively.  
