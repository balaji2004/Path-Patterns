# Walking Pattern & Environmental Impact Calculator

This MATLAB program calculates walking patterns, step counts, and their environmental impact based on GPS data (latitude and longitude). It also provides an estimate of calories burned and the potential carbon offset equivalent to trees planted.

## Features
- **Step Calculation:** Measures the total number of steps based on GPS data.
- **Calories Burned:** Estimates calories burned based on user input for weight and step count.
- **Carbon Offset:** Calculates the reduction in CO2 emissions based on the distance walked.
- **Tree Equivalent:** Converts the carbon offset into an equivalent number of trees needed to offset that amount of CO2.
- **Graphical Plot:** Visualizes the walking route on a map (latitude and longitude plot).

---

## How It Works

1. **Data Input:**
   The program loads the sensor data (including latitude, longitude, and time) from a `.mat` file.
   ```matlab
   load('clutch.mat') % Replace 'clutch.mat' with your actual sensor data file
   ```

2. **Time Calculation:**
   The `timeElapsed` function converts the timestamps from your sensor data into a sequence of elapsed time values.

3. **Distance & Steps Calculation:**
   Using the latitude and longitude data points, the program calculates the total distance traveled and then estimates the number of steps using an average stride length.

4. **Environmental Impact Calculation:**
   The program estimates the calories burned, CO2 emissions reduced, and the number of trees that would absorb an equivalent amount of CO2.

5. **Graphical Output:**
   The route is plotted, showing your path with markers indicating the start and end points.

---

## Requirements

- MATLAB R2022a or later.
- Sensor data obtained from MATLAB Mobile.
- A `.mat` file containing GPS data, specifically `Position.latitude`, `Position.longitude`, and `Position.Properties.RowTimes`.

---

## Instructions to Run

1. **Obtain Sensor Data from MATLAB Mobile:**
   - Download the MATLAB Mobile app (available on Android and iOS).
   - Start recording sensor data on your phone. This includes GPS data, accelerometer data, and timestamps.
   - Upload the recorded data to MATLAB Cloud and download the `.mat` file to your desktop MATLAB environment.

2. **Run the Program:**
   - Load your sensor data into the workspace by replacing the line `load('clutch.mat')` with your own file, e.g., `load('mydata.mat')`.
   - Execute the script to calculate the walking pattern, total steps, and environmental impact.
   - Adjust the `weight` and `steps` variables as needed for a more personalized calculation of the environmental impact.

---

## Sample Output
You can include an example graph of the walking route and sample output values (steps, distance, calories burned, carbon offset, trees planted equivalent) here.

---

**Example Graph:**
[*(img\output.jpge)*]

---

**Sample Output:**
```
Calories Burned: 500 calories
Carbon Offset: 2,020 grams CO2 (2.02 kg CO2)
Equivalent Trees Planted: 0.018517 🌱 trees
```

---

## License

This project is open-source and free to use.