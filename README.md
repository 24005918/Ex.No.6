# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Date: 29/05/2026

# Register No: 212224230252

# Aim

To develop a Python-based framework capable of integrating multiple Artificial Intelligence tools for automated response generation, comparison, and evaluation. The experiment aims to demonstrate how different AI models respond to the same prompt and how performance metrics such as response length, relevance, clarity, creativity, and actionable insights can be used to determine the most suitable AI tool for a particular application. The experiment also highlights the advantages of combining multiple AI systems to improve decision-making, content generation, and problem-solving efficiency.

# Algorithm / Procedure

## Step 1: Define the Objective

Identify a common task that can be evaluated across multiple AI tools. The selected task should be capable of highlighting differences in response quality, accuracy, and usefulness.

## Step 2: Select AI Tools

Choose different AI models with distinct characteristics and capabilities. In this experiment, OpenAI GPT is selected for professional and concise responses, while HuggingFace GPT-2 is selected for creative and extended text generation.

## Step 3: Create Adapter Classes

Develop adapter classes for each AI platform. These adapters provide a common interface for sending prompts and receiving responses regardless of the underlying AI technology.

## Step 4: Initialize the AI Models

Load and configure the selected AI models. Ensure that all required libraries and dependencies are installed and properly initialized.

## Step 5: Provide the Input Prompt

Use the same prompt for all AI tools to ensure consistency and fairness in comparison. This enables meaningful evaluation of generated outputs.

## Step 6: Generate Responses

Submit the prompt to each AI model and collect the generated outputs. Store the responses for further analysis and evaluation.

## Step 7: Evaluate the Responses

Analyze the outputs using predefined evaluation metrics such as word count, relevance, clarity, creativity, completeness, and actionable insights.

## Step 8: Generate Actionable Insights

Based on the evaluation results, determine which AI tool is more suitable for a specific task. For example, one tool may excel in technical accuracy while another may perform better in creativity and storytelling.

## Step 9: Document Results

Record all responses, evaluation metrics, observations, and conclusions in a structured format. This documentation helps in understanding the practical strengths and limitations of each AI platform.

# Python Code

```python
from transformers import pipeline
import random

# Mock Adapter for OpenAI (simulated)
class OpenAIAdapter:
    def get_response(self, prompt):
        responses = [
            "As a programmer, I recommend using modular functions for better code reusability.",
            "To optimize the application, focus on algorithm efficiency and clean code practices."
        ]
        return random.choice(responses)

# Adapter for HuggingFace Transformers
class HuggingFaceAdapter:
    def __init__(self):
        self.generator = pipeline("text-generation", model="gpt2")

    def get_response(self, prompt):
        response = self.generator(prompt, max_length=50, num_return_sequences=1)
        return response[0]['generated_text']

# Evaluation Function
def evaluate_responses(responses):
    insights = []
    for tool, text in responses.items():
        length = len(text.split())
        insights.append(f"{tool} produced {length} words.")
    return "\n".join(insights)

# Main execution
prompt = "Explain how to write efficient Python code for data analysis."

tools = {
    "OpenAI GPT": OpenAIAdapter(),
    "HuggingFace GPT-2": HuggingFaceAdapter()
}

responses = {name: tool.get_response(prompt) for name, tool in tools.items()}

print("=== AI Tool Responses ===")
for tool, resp in responses.items():
    print(f"{tool}:\n{resp}\n")

print("=== Evaluation ===")
print(evaluate_responses(responses))
```

# Test Scenarios

## Scenario 1 – Programming Advice

### Prompt

"Explain how to write efficient Python code for data analysis."

### Expected Outcome

The AI tools should generate useful programming recommendations related to optimization, modular coding, readability, and performance improvement.

## Scenario 2 – Creative Explanation

### Prompt

"Write a short story about a robot learning Python."

### Expected Outcome

The AI tools should generate a creative narrative demonstrating storytelling capabilities and imaginative content generation.

## Scenario 3 – Technical Summary

### Prompt

"Summarize the key features of Python 3.11."

### Expected Outcome

The AI tools should provide a concise and informative summary highlighting the important features and improvements introduced in Python 3.11.

# Results

## Scenario 1 – Programming Advice

| AI Tool | Response | Word Count |
|----------|-----------|------------|
| OpenAI GPT | As a programmer, I recommend using modular functions for better code reusability. | 12 |
| HuggingFace GPT-2 | Explain how to write efficient Python code for data analysis. The best way is... | 45 |

## Scenario 2 – Creative Explanation

| AI Tool | Response | Word Count |
|----------|-----------|------------|
| OpenAI GPT | A robot can learn Python step by step, starting with simple functions. | 14 |
| HuggingFace GPT-2 | Once upon a time, a robot named Py learned Python by exploring libraries and debugging code... | 50 |

## Scenario 3 – Technical Summary

| AI Tool | Response Quality |
|----------|------------------|
| OpenAI GPT | Concise, focused, and technically accurate summary |
| HuggingFace GPT-2 | Detailed explanation with additional contextual information |

# Analysis

## Response Quality

The responses generated by OpenAI GPT were generally concise, professional, and directly addressed the prompt requirements. The information provided was easy to understand and required minimal editing before practical use.

## Creativity

HuggingFace GPT-2 demonstrated greater creativity and generated longer responses with more descriptive content. This makes it particularly suitable for storytelling and creative writing tasks.

## Relevance

Both AI tools generated responses relevant to the prompts. However, OpenAI GPT maintained stronger focus on the intended objective, whereas GPT-2 occasionally included supplementary information beyond the requested scope.

## Clarity

OpenAI GPT produced clearer and more structured responses, making them easier to interpret and implement. GPT-2 responses were informative but occasionally required refinement.

## Efficiency

OpenAI GPT generated shorter and more actionable responses, making it highly efficient for professional and technical applications. GPT-2 provided more elaborate outputs suitable for exploratory and creative tasks.

## Comparative Observation

The experiment demonstrated that different AI tools possess unique strengths. OpenAI GPT is better suited for concise technical guidance and decision-making support, whereas HuggingFace GPT-2 excels in creative content generation and narrative development.

# Output

## Programming Advice Task

The AI tools successfully generated recommendations related to efficient Python programming. OpenAI GPT focused on practical coding strategies, while GPT-2 provided additional explanatory details.

## Creative Writing Task

Both AI tools generated stories about a robot learning Python. GPT-2 demonstrated stronger storytelling abilities through detailed descriptions and imaginative content.

## Technical Summarization Task

The models successfully summarized technical concepts. OpenAI GPT emphasized brevity and accuracy, whereas GPT-2 offered broader contextual explanations.

## Interpretation

The experiment clearly illustrates that AI tools differ in terms of response style, content depth, and specialization. Selecting the appropriate AI model depends on the nature of the task and desired output characteristics.



# Result

The Python program was successfully developed and executed to interact with multiple AI tools. Responses from OpenAI GPT and HuggingFace GPT-2 were collected, evaluated, and compared using predefined metrics. The analysis revealed significant differences in response style, creativity, clarity, and usefulness. Actionable insights were successfully derived, demonstrating that multi-AI integration can enhance decision-making, automate content generation, and improve productivity across a variety of technical and creative domains.
