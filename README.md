# project name: android app using Gen AI mahilla shakthi-Micro finance

## table of content
## Project Description:
Mahila Shakti Unnati is a simple Android application developed using Kotlin and Jetpack Compose to support women through a basic micro-finance loan eligibility system. The app allows users to enter their name, monthly income, and required loan amount to check whether they are eligible for a loan.
The main purpose of this project is to demonstrate how technology can simplify financial assistance processes for women entrepreneurs and self-help groups. The application uses a simple eligibility logic where the loan is approved if the requested amount is within a limit based on the user’s monthly income.
The app provides a clean and user-friendly interface with input fields and an instant result display. It is designed for beginners to understand Android app development concepts such as UI design, state management, user input handling, conditional statements, and button click actions using Jetpack Compose.
This project is part of an Android App Development using Generative AI learning program and helps in building practical mobile application development skills. Future improvements may include Firebase database integration, AI-based financial suggestions, EMI calculation, multilingual support, and secure user authentication.
## Features: 
User-friendly interface developed using Jetpack Compose 
Allows users to enter name, monthly income, and loan amount
Checks loan eligibility instantly based on income
Displays loan approval or rejection message
Simple and clean design for easy usage
Uses Kotlin programming language for Android development
Demonstrates state management and user input handling
Helps understand basic micro-finance application concepts
Beginner-friendly Android project for learning purposes
Can be upgraded with AI features, Firebase, and EMI calculation in future
## Technology used: 
Kotlin – Main programming language used for Android app development 
Android Studio – IDE used to build and run the application 
Jetpack Compose – Modern UI toolkit used for designing the app interface 
Material 3 – Used for responsive and attractive UI components 
Android SDK – Provides tools and libraries for Android development 
State Management (remember & mutableStateOf) – Used to handle user input and UI updates dynamically 
ComponentActivity – Base Android activity class used in the application 	
Gradle – Build automation tool used for dependency management and project configuration
## Installation Steps:
•	Install Android Studio on your computer. 
•	Open Android Studio and select New Project or open the existing project folder. 
•	Copy the project code into the MainActivity.kt file. 
•	Make sure the required dependencies for Jetpack Compose and Material 3 are added in the Gradle files. 
•	Click Sync Project with Gradle Files to download dependencies. 
•	Connect an Android device or start an emulator from Android Studio. 
•	Click the Run ▶️ button to build and launch the application. 
•	The app will open on the device, where users can enter income and loan details to check loan eligibility.
## Usage
1.	Open the Mahila Shakti Unnati application on your Android device or emulator. 
2.	Enter the user’s name in the Name field. 
3.	Enter the monthly income in the Monthly Income field. 
4.	Enter the required loan amount in the Loan Amount field. 
5.	Click the Check Eligibility button. 
6.	The application will process the details and display either: 
o	Loan Approved if the user is eligible 
o	Loan Rejected if the requested loan exceeds the eligibility limit 
7.	Users can modify the details and check eligibility again anytime. 

## CODE:

package com.example.myapplication

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.layout.*
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Modifier
import androidx.compose.ui.unit.dp

class MainActivity : ComponentActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        setContent {
            MahilaShaktiApp()
        }
    }
}

@Composable
fun MahilaShaktiApp() {

    var name by remember {
        mutableStateOf("")
    }

    var income by remember {
        mutableStateOf("")
    }

    var loan by remember {
        mutableStateOf("")
    }

    var result by remember {
        mutableStateOf("")
    }

    MaterialTheme {

        Column(
            modifier = Modifier
                .fillMaxSize()
                .padding(20.dp)
        ) {

            Text(
                text = "Mahila Shakti Unnati",
                style = MaterialTheme.typography.headlineMedium
            )

            Spacer(modifier = Modifier.height(20.dp))

            OutlinedTextField(
                value = name,
                onValueChange = {
                    name = it
                },
                label = {
                    Text("Enter Name")
                },
                modifier = Modifier.fillMaxWidth()
            )

            Spacer(modifier = Modifier.height(10.dp))

            OutlinedTextField(
                value = income,
                onValueChange = {
                    income = it
                },
                label = {
                    Text("Monthly Income")
                },
                modifier = Modifier.fillMaxWidth()
            )

            Spacer(modifier = Modifier.height(10.dp))

            OutlinedTextField(
                value = loan,
                onValueChange = {
                    loan = it
                },
                label = {
                    Text("Loan Amount")
                },
                modifier = Modifier.fillMaxWidth()
            )

            Spacer(modifier = Modifier.height(20.dp))

            Button(
                onClick = {

                    result =
                        if (income.isNotEmpty() && loan.isNotEmpty()) {

                            val incomeValue = income.toInt()
                            val loanValue = loan.toInt()

                            if (loanValue <= incomeValue * 10) {
                                "Loan Approved for $name"
                            } else {
                                "Loan Rejected"
                            }

                        } else {
                            "Enter all details"
                        }
                },
                modifier = Modifier.fillMaxWidth()
            ) {

                Text("Check Eligibility")
            }

            Spacer(modifier = Modifier.height(20.dp))

            Text(
                text = result,
                style = MaterialTheme.typography.headlineSmall
            )
        }
    }
} 
## Conclusion
The Mahila Shakti Unnati application is a beginner-friendly Android project developed using Kotlin and Jetpack Compose. It demonstrates how mobile applications can be used to simplify basic financial processes such as loan eligibility checking. The project helps in understanding important Android development concepts like user input handling, state management, UI design, and conditional logic.This application also highlights the idea of supporting women through simple digital financial solutions. Although the current version includes only basic eligibility checking, it can be further improved with advanced features such as AI-based recommendations, Firebase integration, EMI calculation, multilingual support, and secure authentication. Overall, the project provides practical experience in Android app development and serves as a strong foundation for building real-world financial applications



