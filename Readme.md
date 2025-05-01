# Ex06 BMI Calculator
## Date:
### Name : Vikram K
### Reg no: 212222040180

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
### BHI.jsx
```
import React, { useState } from 'react';

const Bmi = () => {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState('');

  const calculateBMI = () => {
    if (!weight || !height) {
      setMessage('Please enter valid weight and height.');
      setBmi(null);
      return;
    }

    const heightInMeters = height / 100;
    const calculatedBMI = (weight / (heightInMeters * heightInMeters)).toFixed(2);
    setBmi(calculatedBMI);

    if (calculatedBMI < 18.5) {
      setMessage('Underweight');
    } else if (calculatedBMI < 24.9) {
      setMessage('Normal');
    } else if (calculatedBMI < 29.9) {
      setMessage('Overweight');
    } else {
      setMessage('Obese');
    }
  };

  return (
    <div className="bmi-box">
        <h2  className="app-container">(BMI) Calculator</h2>
      <div className="input-group">
        <label>Weight (kg):</label>
        <input
          type="number"
          placeholder="e.g. 60"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
      </div>

      <div className="input-group">
        <label>Height (cm):</label>
        <input
          type="number"
          placeholder="e.g. 170"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
      </div>

      <button onClick={calculateBMI}>Calculate</button>

      {bmi && (
        <div className="result">
          <h3>Your BMI: {bmi}</h3>
          <p>Status: {message}</p>
        </div>
      )}
    </div>
  );
};

export default Bmi;
```
### index.css
```
body {
  font-family: Arial, sans-serif;
  background: linear-gradient(50deg,rgb(106, 106, 210),rgb(238, 238, 106),rgb(78, 78, 224));
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;

}

.app-container {
  text-align: center;
}

.bmi-box {
  background-color: #ffffff;
  padding: 30px;
  border-radius: 12px;
  width: 320px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  margin-top: 20px;
}

.input-group {
  margin: 20px 0;
  text-align: left;
}

.input-group label {
  display: block;
  margin-bottom: 6px;
  font-weight: bold;
}

.input-group input {
  width: 100%;
  padding: 10px;
  font-size: 15px;
  border: 1px solid #ccc;
  border-radius: 8px;
}

button {
  margin-top: 15px;
  padding: 10px 25px;
  font-size: 16px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s ease-in-out;
}

button:hover {
  background-color: #388e3c;
}

.result {
  margin-top: 25px;
  text-align: center;
}

.result h3 {
  margin: 0;
  font-size: 24px;
}

.result p {
  font-size: 18px;
  color: #555;
}
```

## OUTPUT

![image](https://github.com/user-attachments/assets/d7e388c1-4839-45fd-80ce-62be4965fe68)

## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
