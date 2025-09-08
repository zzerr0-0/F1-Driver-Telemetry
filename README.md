🏎️ **F1 Driver Telemetry Analysis:**

Hello again, this is my AI-powered Formula 1 driver performance project. My goal is to explore real telemetry data to understand how drivers perform on the track, and to eventually build models that can predict performance, detect fatigue, or even analyze driving styles.

This project is my first attempt to integrate mechanical systems, artificial intelligence, and actual racing data.  Since I'm still learning Python and AI, I worked on it for about two weeks, changing and experimenting with the code as I went along. In addition to the fact that I've learnt a lot in the last few weeks, it was a terrific way for me to practice and gain confidence.
 
🏎️ Project Overview:

This project retrieves official Formula 1 telemetry data using Python and the FastF1 module.
 It enables you to:

 > Compare the fastest laps of two drivers during a certain session.

 > Show where drivers halt, accelerate, or maintain top speed by visualizing speed versus track distance.

 > Create the foundation for future AI-based driver analysis (such as style classification or fatigue identification).

🏎️ Features

> makes use of the FastF1 Python module to retrieve authentic F1 telemetry.
> compares a few drivers' braking, throttle, and speed habits.
> enables the creation of accessible, understandable graphs for visual performance comparison.
> Completely adaptable to dashboards or machine learning algorithms.

🏎️ Requirements:

  🏁Python 3.x
  🏁Anaconda (recommended for notebooks and package management)

🏎️ Libraries:

pip install fastf1 matplotlib pandas

🏎️ Setup & Usage:
*This is the important part as Im showing u the way around how to make the repository work*

1. Clone or download this repository

2. You open Jupyter Notebook via Anaconda Navigator

3. Open the notebook GRANPREMIO2023F1.ipynb

4. Run the cells step by step. Here, I did the code to compare Verstappen and Hamilton:

import fastf1
from fastf1 import plotting
import matplotlib.pyplot as plt

# Enable caching for faster future runs
fastf1.Cache.enable_cache('cache')

# Load session (2023 Spanish GP Qualifying)
session = fastf1.get_session(2023, 'Spain', 'Q')
session.load()

# Pick fastest laps for each driver
ver = session.laps.pick_driver('VER').pick_fastest()
ham = session.laps.pick_driver('HAM').pick_fastest()

# Get telemetry data
ver_tel = ver.get_car_data().add_distance()
ham_tel = ham.get_car_data().add_distance()

# Plot speed comparison
plt.figure(figsize=(12,6))
plt.plot(ver_tel['Distance'], ver_tel['Speed'], label='Verstappen')
plt.plot(ham_tel['Distance'], ham_tel['Speed'], label='Hamilton')
plt.xlabel('Distance (m)')
plt.ylabel('Speed (km/h)')
plt.title('Fastest Lap Speed Comparison - Spain 2023 Quali')
plt.legend()
plt.show()

---

🏎️ What You’ll See :

> A graph of speed vs. distance for both drivers’ fastest laps

> Differences in braking points, acceleration zones, and top speeds

> Insights into driving style and performance patterns

---

🏎️ Next Steps / Future Development: 

> Add throttle and brake comparisons for deeper analysis.

> Integrate video analysis for driver fatigue detection using computer vision.

> Train ML models to predict lap times or classify driving styles.

> Build a dashboard to visualize multiple drivers, laps, and sessions interactively.

---

🏎️ Folder Structure

F1-Driver-Telemetry/
│
├─ GRANPREMIO2023F1.ipynb     # Main Jupyter Notebook
├─ README.md                  # Project description
├─ .gitignore                 # Files/folders to ignore on GitHub
└─ cache/                     # FastF1 cache folder (ignored in git)

---

🏁 License

*This project is licensed under the MIT License; feel free to use and learn from it, but please give credit if you share or build upon it.*

---

🏎️ About Me

I’m Rania Karakhi, an AI enthusiast with a passion for data science and mechanical systems who is a long-term fan of Formula 1.
This project took me 2 weeks to modify and work my way through, and it’s one of my first hands-on experiences in Python and AI.
It’s just the beginning of my journey; one lap, one dataset, one model at a time!! 🏁
