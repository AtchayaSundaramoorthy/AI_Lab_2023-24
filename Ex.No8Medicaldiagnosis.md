# Ex No: 8 - Logic Programming: Medical Diagnosis Expert System

**Date:** 22-04-2025  
**Register Number:** 212222040021 

## AIM:  
Write a Prolog program to build a Medical Diagnosis Expert System.

## ALGORITHM:  
1. Start the program.  
2. Write rules for each disease.  
3. If patient has mumps, symptoms include fever and swollen glands.  
4. If patient has cough, sneeze, and runny nose, the disease is measles.  
5. If patient has headache, sneezing, sore throat, runny nose, and chills, the disease is common cold.  
6. Define rules for all diseases.  
7. Call the predicates, collect symptoms of the patient, and give the diagnosis hypothesis.

## PROGRAM:
```prolog
hypothesis(Patient, german_measles) :-
    symptom(Patient, fever),
    symptom(Patient, headache),
    symptom(Patient, runny_nose),
    symptom(Patient, rash).

hypothesis(Patient, flu) :-
    symptom(Patient, fever),
    symptom(Patient, headache),
    symptom(Patient, body_ache),
    symptom(Patient, conjunctivitis),
    symptom(Patient, chills),
    symptom(Patient, sore_throat),
    symptom(Patient, runny_nose),
    symptom(Patient, cough).

hypothesis(Patient, common_cold) :-
    symptom(Patient, headache),
    symptom(Patient, sneezing),
    symptom(Patient, sore_throat).

hypothesis(Patient, chicken_pox) :-
    symptom(Patient, fever),
    symptom(Patient, chills),
    symptom(Patient, body_ache),
    symptom(Patient, rash).

hypothesis(Patient, measles) :-
    symptom(Patient, cough),
    symptom(Patient, sneezing),
    symptom(Patient, runny_nose).

hypothesis(Patient, mumps) :-
    symptom(Patient, fever),
    symptom(Patient, swollen_glands).

symptom(raju, headache).
symptom(raju, sneezing).
symptom(raju, sore_throat).

symptom(kumar, fever).
symptom(kumar, headache).
symptom(kumar, runny_nose).
symptom(kumar, rash).

symptom(sita, fever).
symptom(sita, headache).
symptom(sita, body_ache).
symptom(sita, conjunctivitis).
symptom(sita, chills).
symptom(sita, sore_throat).
symptom(sita, runny_nose).
symptom(sita, cough).
```

### Output:
![image](https://github.com/user-attachments/assets/6b3b8da9-01fb-4e93-88e2-333fe4b808c2)

### Result:
Thus, a simple medical diagnosis expert system was successfully built using Prolog.
