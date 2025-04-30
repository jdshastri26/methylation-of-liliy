# methylation-of-liliy


import time
import csv
from datetime import datetime

# Define the methylation workflow
workflow_steps = [
    {"step": "Leaf extraction in methanol (overnight soak)", "duration_min": 60},
    {"step": "Filtration and concentration of extract", "duration_min": 20},
    {"step": "Dissolve extract in acetone", "duration_min": 5},
    {"step": "Add K₂CO₃ base to reaction mixture", "duration_min": 3},
    {"step": "Slow addition of dimethyl sulfate (ice bath)", "duration_min": 15},
    {"step": "Stirring at 40°C", "duration_min": 180},
    {"step": "Quench reaction with water", "duration_min": 5},
    {"step": "Extract product with ethyl acetate", "duration_min": 10},
    {"step": "Dry with sodium sulfate and concentrate", "duration_min": 15},
    {"step": "TLC or HPLC analysis", "duration_min": 20}
]

# Output file setup
log_file = "lily_leaf_methylation_log.csv"
with open(log_file, mode='w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(["Timestamp", "Step Description", "Expected Duration (min)", "Status"])

# Display header
print("🔬 Lily Leaf Methylation Process Tracker")
print("Starting process...\n")

# Simulate execution of each step
for i, task in enumerate(workflow_steps, start=1):
    step_desc = task["step"]
    duration = task["duration_min"]
    timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")

    # Simulate and log the step
    print(f"Step {i}: {step_desc} — Estimated Duration: {duration} min")
    with open(log_file, mode='a', newline='') as file:
        writer = csv.writer(file)
        writer.writerow([timestamp, step_desc, duration, "Completed"])

    time.sleep(0.5)  # Simulated delay for demo (adjust to 1 for real-time logging)

# Final message
print("\n✅ Process completed successfully.")
print(f"Log file saved as: {log_file}")
