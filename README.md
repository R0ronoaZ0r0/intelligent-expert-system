# INTELLIGENT EXPERT SYSTEM FOR DIAGNOSING TOXIC SUBSTANCES AND POISONS

# Run:
Compile using:
g++ backwardChain.h backwardChain.cpp forwardChain.h forwardChain.cpp main.cpp

And then run using:
./a.exe

# 1. Problem Description  
1.1. Problem Statement: Create an intelligent computer expert system for an emergency room of a hospital to diagnose toxic substances and poisons and to recommend treatment based on the diagnosis.  
1.2. Description:  
Poisoning is injury or death due to swallowing, inhaling, touching, or injecting various drugs, chemicals, venoms, or gases. Toxic substances and poisons are harmful and in most cases are life threatening to living beings. In most cases, the patient has to be treated quickly with the right treatment. Administering a wrong treatment may cause further harm, due to unknown reactions. So, in the emergency room, it becomes very crucial to have a reliable system for both the diagnosis of toxic substances and poisons and the corresponding accurate treatment to avoid any mistakes that may cause further harm or even death.  
This project offers a solution to the above problem by using an intelligent computer expert system to diagnose toxic substances and poisons and to recommend treatment based on the diagnosis in an emergency room of a hospital. This project has a user-friendly interface, which receives input data from emergency room staff in a restricted English format, uses keyword matching, and responds in a restricted English format. The emergency room staff will feed the symptoms of the patient. Using Backward Chaining, the expert system will diagnose the toxic substance or the poison, and then using Forward Chaining, it will recommend the treatment.  

# 2. Domain  
Diagnosis and treatments for poisons and toxic substances, Intelligent expert system. Forward referencing, Backward referencing.  
2.1. Intelligent Expert Systems:  
In artificial intelligence, an expert system is a computer system emulating the decision-making ability of a human expert. Expert systems are designed to solve complex problems by reasoning through bodies of knowledge, represented mainly as if–then rules rather than through conventional procedural code. Intelligent expert systems consist of three main parts:  
• Knowledge Base  
• Inference Engine • Interface  
2.1.1. Knowledge Base: The knowledge base represents facts and rules. Facts for a knowledge base must be acquired from human experts through interviews and observations. This knowledge is then usually represented in the form of “if-then” rules (production rules): “If some condition is true, then the following inference can be made (or some action taken).” The knowledge base of a major expert system includes thousands of rules. A probability factor is often attached to the conclusion of each production rule and to the ultimate recommendation because the conclusion is not a certainty.  
2.1.2. Inference Engine: The inference engine applies the rules to the known facts to deduce new facts. This process would iterate as each new fact in the knowledge base could trigger additional rules in the inference engine. Inference engines work primarily in one of two modes either special rule or facts: forward chaining and backward chaining. Forward chaining starts with the known facts and asserts new facts. Backward chaining starts with goals and works backward to determine what facts must be asserted so that the goals can be achieved.   
2.1.3. Interface: A user interface is the method by which the expert system interacts with a user. These can be through dialog boxes, command prompts, forms, or other input methods. Some expert systems interact with other computer applications and do not interact directly with a human. 

# 3. Methodologies  
3.1. Backward Chaining:  
Backward chaining is also known as a goal-driven approach. It gives the output based on the goal. First, the inference engines ask for the conclusion and then chain backward. This project uses backward chaining to determine the kind of toxic substance or poison with which the patient is affected. The system questions the user and considers the goal node. We define the knowledge base where there are some predefined rules. These rules contain the conclusion i.e., the goal node. It considers the consequent and extracts facts from the antecedent.  
3.1.1. Data Structures in Backward Chaining:   
3.1.1.1. Conclusion List:    
It lists all the possible conclusions in sequential order. This data structure contains three items Rule number, Conclusion associated with the rule number and the set of conditions that yield the conclusion. We scan the conclusion list in backward chaining.  
3.1.1.2. Variable List:  
All the variables present in the rules are stored in this list. This data structure contains two items i.e., the variable name for each one contained in the IF part and whether the variable is instantiated or not.  
3.1.1.3. Clause Variable list:  
This list contains all the variables that are present in the IF conditions. For each rule, we store the variables and the remaining spaces are left off with a blank space. How many blank spaces need to be left is based on the maximum variables that are present in the IF condition. The variables in the IF part are chained with the AND operator.  
A formula is derived in order to calculate the clause variable number of the rule:  
Clause number = 12 *((Rulenumber/10) - 1) + 1  

Here the number 12 is the number of spaces given for each rule and the 10 represents the difference between the numbering of the rules. 
 3.1.1.4. Conclusion Stack:  
This data structure is the most important aspect of the backward chain implementation. This indicates which IF-THEN statement has the desired result and which clause in the IF section is being tested for instantiation.  
3.2. FORWARD CHAINING:    
Forward chaining is also known as a fact driven approach. It gives the output based on the facts. It checks if the antecedent is satisfied or not. It prompts the user with the questions and records them. It provides the output based on the input given by the user. In this project the system provides the preferred treatment for the particular poison.  
3.2.1. Data Structures used in Forward Chaining: 3.2.1.1. Clause Variable list:  
This list contains all the variables that are present in the IF conditions. For each rule we store the variables and the remaining spaces are left off with a blank space. How many blank spaces need to be left is based on the maximum variables that are present in the IF condition.  
A formula is derived in order to calculate the Rule number:  
Rule number = {(Quotient (clause number)/12)} +1) *10  
Here the number 12 is the number of spaces given for each rule and the 10 represents the difference between the numbering of the rules. 
3.2.1.2. Conclusion Variable queue:  
This data structure is the most important aspect of the forward chain implementation. This indicates which IF-THEN statement has the desired result and which clause in the IF section is being tested.  
3.2.1.3. Variable list:  
All the variables present in the rules are stored in this list. This data structure contains two items i.e., the variable name for each one contained in the IF part and whether the variable is instantiated or not.  
3.2.1.4. Clause Variable pointer:  
This keeps track of the rule number and the clause number of the current IF-THEN condition being examined.  
