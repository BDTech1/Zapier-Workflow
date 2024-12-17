# Zapier-Workflow
Zapier workflow for automating alternative value propositions and Generate user persona.


# Zapier Workflow: Automating Alternative Value Propositions and Generating Automated User Persona

## Description
This repository contains the Zapier workflow configuration for automating:
- **Alternative Value Propositions** **User Persona Generating From Tally Form** using ChatGPT.
- Updating the user persona in Airtable.
- Sending email notifications to administrators for review.


-------------------------------------------------------------------------------------
## Workflow Steps for User persona 

### 1. Trigger Configuration with Tally.so 

### 2. ChatGPT Prompt

### 3. Code by Zapier (JavaScript)

### 4. Create Documents in Google Docs

### 5. Airtable Update

### 6. Notify Client 
---------------------------------------------------------------------------------------

## code by Zapier for auto formation in the Database

// Safely access and log the raw response
const rawResponse = inputData.response || {};
console.log("Raw Response:", rawResponse);


// Extract the data directly from the raw response
let data;
try {
  data = typeof rawResponse === "string" ? JSON.parse(rawResponse) : rawResponse; // Handle both string and object
} catch (error) {
  console.error("Error parsing raw response:", error);
  data = {}; // Fallback to empty object if parsing fails
}



// Log parsed data for debugging
console.log("Parsed Data:", data);

// Return structured data with fallbacks for missing fields
return {
  fullName: data["Full Name"] || "Not Provided",
  emailAddress: data["Email Address"] || "Not Provided",
  demographicInfo: {
    gender: data["Demographic Information"]?.Gender || "Not Provided",
    age: data["Demographic Information"]?.Age || "Not Provided",
    incomeLevel: data["Demographic Information"]?.["Income Level"] || "Not Provided",
    nrsSocialGrade: data["Demographic Information"]?.["NRS Social Grade and Description"] || "Not Provided",
    familyStatus: data["Demographic Information"]?.["Family Status"] || "Not Provided",
  },

  
  psychographicInfo: {
    interests: data["Psychographic Information"]?.Interests || ["Not Provided"],
    values: data["Psychographic Information"]?.Values || ["Not Provided"],
    lifestyle: data["Psychographic Information"]?.Lifestyle || ["Not Provided"],
  },


  
  personaGoals: data["Persona Goals"] || ["Not Provided"],
  painPoints: data["Pain Points"] || ["Not Provided"],
  behavioralPatterns: {
    productUsage: data["Behavioral Patterns and Customer Stories"]?.["Product Usage"] || "Not Provided",
    decisionMaking: data["Behavioral Patterns and Customer Stories"]?.["Decision-Making Processes"] || "Not Provided",
    preferredChannels: data["Behavioral Patterns and Customer Stories"]?.["Preferred Communication Channels"] || "Not Provided",
  },
};





----------------------------------------------------------------------------------------------------------------------------------------------------




## Workflow Steps for 3 Alternative Value Proposition

### 1. Trigger Configuration with Airtable Database 

### 2. ChatGPT Prompt for Generating Value Proposition

### 3. Code by Zapier (JavaScript)

### 5. Airtable Update

### 6. Notify Client 





## Code By Zapier 

const response = inputData.response || "";

// Log the raw response for debugging purposes
console.log("Raw response:", response);

// Use regex to match the value propositions based on the format: numbered points "1.", "2.", "3." followed by text
const propositions = response.match(/\d\.\s.*?:(.*?)(?=\n\d\.|$)/gs) || [];

// Log the extracted propositions for debugging
console.log("Extracted propositions:", propositions);

// Clean and map each proposition into separate fields
return {
    proposition1: propositions[0] ? propositions[0].replace(/^1\.\s.*?:/, "").trim() : "Not Provided",
    proposition2: propositions[1] ? propositions[1].replace(/^2\.\s.*?:/, "").trim() : "Not Provided",
    proposition3: propositions[2] ? propositions[2].replace(/^3\.\s.*?:/, "").trim() : "Not Provided",
};

--------------------------------------------------------------------------------------------------------------------------


## Author
Team 12, Abu Sufiun | abusufians808@gmail.com

