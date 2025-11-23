# HARSIMAR SINGH 25BCY10230
import pandas as pd
import numpy as np
from sklearn.linear_model import LinearRegression
import matplotlib.pyplot as plt



historical = {
    'total':    [10, 15, 21, 25, 30, 35, 40, 45, 50, 54],
    'went':     [8,  12, 16, 20, 27, 30, 35, 39, 45, 48],
    'perc':    [80.0,80.0,80.0,80.0,90.0,85.7,87.5,86.6,90.0,87.2]
}

df = pd.DataFrame(historical)

print("training on old data ")
print(df)
print()

X = df[['total','went']]
y = df['perc']

model = LinearRegression()
model.fit(X, y)

score = model.score(X,y) * 100
print(f"model finished {score:.1f}%  ")
print("-" * 55)


print("now tell me your attendance\n")

while True:
    try:
        total_classes = int(input("total classes happened till now → "))
        attended = int(input("classes you actually showed up for → "))
        
        if attended > total_classes:
            print("wrong input")
            continue
        if total_classes <= 0 or attended < 0:
            print("wrong input given")
            continue
        break
    except:
        print("enter")

# prediction time
pred = model.predict([[total_classes, attended]])[0]

print("\n" + "="*55)
print(f" predicted attendance is given by→ {pred:.2f}%")
print("="*55)

if pred >= 75:
    print("  YOU'RE SAFE ")
    
else:
    
    needed = int(np.ceil((0.75 * total_classes) - attended))
    if needed <= 0:
        print("  you need to improve")
    else:
        print(f"   DANGER ZONE: attend next {needed} classes NON-STOP ")
print("="*55)




plt.figure(figsize=(10,6))
plt.scatter(df['went'], df['perc'], color='skyblue', s=100, edgecolor='black', label='Old semesters data')
plt.scatter(attended, pred, color='red', s=300, marker='X', edgecolor='darkred', linewidth=3, label='You right now')


plt.plot(df['went'], model.predict(df[['total','went']]), color='orange', linewidth=2)

plt.axhline(75, color='gray',  linewidth=3, label='75%')

plt.title("Attendance  Check ",)
plt.xlabel("Classes You Actually Attended", )
plt.ylabel("Attendance Percentage", )
plt.legend()
plt.grid(True, alpha=0.3)
plt.tight_layout()
plt.show()
