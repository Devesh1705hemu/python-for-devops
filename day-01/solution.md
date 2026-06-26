import psutil

def check(name, value, threshold):
    if value > threshold:
        print(name, "threshold exceeded!")
    else:
        print(name, "is normal.")

cpu_threshold = int(input("Enter CPU threshold: "))
memory_threshold = int(input("Enter Memory threshold: "))
disk_threshold = int(input("Enter Disk threshold: "))

cpu = psutil.cpu_percent(interval=1)
memory = psutil.virtual_memory().percent
disk = psutil.disk_usage("/").percent

check("CPU", cpu, cpu_threshold)
check("Memory", memory, memory_threshold)
check("Disk", disk, disk_threshold)
