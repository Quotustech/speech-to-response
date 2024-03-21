# Speech to Text Converter

Speech to Text Converter

This project provides a Speech to Text Converter component for React applications, utilizing the OpenAI API for processing speech input. It allows users to convert spoken words into text and extract specific information such as dates, locations, and counts of persons, children, and adults from the spoken content.

# Installation

To install the Speech to Text Converter component, use npm:

npm install speech_to_text_converter

# Usage :

Import the Speech to Text Converter component and necessary dependencies:
```typescript
import React, { useState } from 'react';
import { SpeechToText } from 'speech_to_text_converter';
import SpeechRecognition, { useSpeechRecognition } from "react-speech-recognition";

 Define interface for storing extracted data
interface JsonStoredData {
  StartingDate: Date | null;
  EndingDate: Date | null;
  Persons: string | null;
  Location: string | null;
  ChildCount: number | null;
  AdultCount: number | null;
  Transcript: string | null;
}
 Define your component
const YourComponent = () => {
  const key: string = process.env.REACT_APP_API_KEY || '';
  const { transcript, browserSupportsSpeechRecognition, resetTranscript } = useSpeechRecognition();
  const [jsonStoredData, setJsonStoredData] = useState<JsonStoredData>({
    StartingDate: null,
    EndingDate: null,
    Persons: null,
    Location: null,
    ChildCount: null,
    AdultCount: null,
    Transcript: null,
  });

  return (
    <div>
      <SpeechToText
        apiKey={key}
        SpeechRecognition={SpeechRecognition}
        resetTranscript={resetTranscript}
        browserSupportsSpeechRecognition={browserSupportsSpeechRecognition}
        transcript={transcript}
        setJsonStoredData={setJsonStoredData}
        mic_color=""
        mic_bg_color='#ee121d50'
      />
    </div>
  );
};

export default YourComponent;
```
Ensure you have set the REACT_APP_API_KEY environment variable with your OpenAI API key.

Use the YourComponent in your application where speech-to-text functionality is required.

# Contributing

Contributions are welcome! Please follow the standard guidelines for contributing to this project.

# License

This project is licensed under the quotus software solutions License.# speech_to_text_converter
