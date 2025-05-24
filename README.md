Automatic Irrigation System using Logistic Regression
This project is a smart automatic irrigation system that uses a logistic regression model to predict whether a water pump should be ON or OFF based on soil moisture readings from an analog sensor.

Components Used
Arduino Uno/Nano
Soil Moisture Sensor (analog)
Water Pump (or an LED for testing)
Relay Module or Transistor Circuit
Jumper Wires
Power Source

Description
This system reads soil moisture values from an analog sensor connected to pin A0, maps the sensor value to a moisture percentage, and calculates the probability of the soil being dry using a logistic regression formula.

Logistic Regression Equation:
probability = 1 / (1 + e^-(27.3629311 + -0.72922093 * percentage))
If the probability is ≥ 0.5, the pump is turned ON.
If the probability is < 0.5, the pump is turned OFF.
This formula is derived from a logistic regression model trained on historical soil moisture data.

Code Explanation
analogRead(A0) reads the raw moisture value.
map(soilMoistureValue, 490, 1023, 100, 0) converts it into a percentage.
The logistic regression formula computes the probability.
digitalWrite(3, HIGH) turns on the pump if necessary.

Serial Monitor Output
Example output:
Moisture Percentage: 25
Probability: 0.78
Pump on

Delay
The system updates every 1 second (delay(1000)).
