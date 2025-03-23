# Question-5
def analyze_power_consumption(data):
    if any(value < 10 or value > 200 for value in data):
        return "INVALID INPUT"
    
    sensors = [0] * 5
    for i in range(5):
        sensors[i] = sum(data[i::5]) 
    
    max_avg = max(sensors)
    
    if max_avg < 50:
        return "Energy consumption is optimal."
    
    return f"Sensor Number: {sensors.index(max_avg) + 1}"

data = [
    120, 110, 90, 85, 80,  
    100, 115, 85, 95, 90,  
    110, 130, 100, 80, 75,  
    105, 125, 95, 100, 85
]

print(analyze_power_consumption(data))
