<picture>
  <source media="(prefers-color-scheme: light)" img width="112" srcset="https://github.com/user-attachments/assets/1e553e8f-5aa8-4bb5-bb49-17670c050c94">
  <source media="(prefers-color-scheme: dark)" img width="112" srcset="https://github.com/user-attachments/assets/95c4b7e2-3d5c-47d0-b3d1-e8753a88976d">
<img width="112" alt="Image" src="https://github.com/user-attachments/assets/1e553e8f-5aa8-4bb5-bb49-17670c050c94"/>
</picture>

ServiceNow &nbsp;&nbsp;|&nbsp;&nbsp; March 19, 2025


# Summary of Issues in LLM Responses

## Original Prompt 

````
You are tasked with creating a high-quality search query for an American Express customer service chatbot. The query should be derived from a given customer support chat. You do not have to respond to the cardmember's message, rather your task is to rewrite their message as a self-contained search query that can be used for retrieving the relevant information from a FAQ Knowledge Base. It's ok to leave the cardmember's message as is if it already appears to be a self-contained query that a search process could find an answer for.
    
## Customer Support Chat:
{chat}
search query:
````

## Prompt Improvement Recommendations

- **Emphasize Clarity and Specificity:** Modify the prompt to explicitly instruct the AI to ensure that search queries are clear, specific, and directly reflect the cardmember's intent without introducing ambiguity.
- **Encourage Direct Statements:** Include a guideline that search queries should be formulated as direct statements rather than questions, maintaining the original intent and clarity of the cardmember's message.
- **Highlight the Importance of Context:** Add a requirement for the AI to consider the entire context of the cardmember's inquiry when generating search queries, ensuring that all relevant details are included.
- **Instruct Against Repetition:** Specify that responses should not simply repeat the cardmember's original message but should instead transform it into a more effective search query that captures the essence of the inquiry.
- **Provide Examples of Effective Queries:** Include examples of well-structured search queries in the prompt to serve as a reference for the AI, illustrating the expected format and specificity needed for effective information retrieval.
<br>

## Example of Recommended Prompt to Consider

_Note: This new prompt is merely a suggestion based on the identified issues. In practice, you may want to make your own adjustments to the original prompt using all of the information contained within this report._ <br>

````
You are tasked with creating a high-quality search query for an American Express customer service chatbot. The query should be derived from a given customer support chat. Your goal is to rewrite the cardmember's message as a self-contained search query that can effectively retrieve relevant information from a FAQ Knowledge Base. 

1. Ensure that the search query is clear, specific, and directly reflects the cardmember's intent without introducing ambiguity.
2. Formulate the search query as a direct statement rather than a question, while maintaining the original intent and clarity of the cardmember's message.
3. Consider the entire context of the cardmember's inquiry to ensure that all relevant details are included in the search query.
4. Transform the cardmember's original message into a more effective search query that captures the essence of the inquiry, avoiding simple repetition of their words.
5. Aim for a well-structured and specific search query that facilitates effective information retrieval.

If the cardmember's message already appears to be a self-contained query suitable for search, you may leave it unchanged. 

## Customer Support Chat:
{chat}
search query: 
````
<br>

## Types of Issues Detected

- **Lack of Specificity and Clarity:** Many responses fail to capture the specific intent of the cardmember's inquiries, resulting in vague or overly simplistic search queries that do not effectively guide the search process.**
  - See clusters (below): 4, 9, 27

- **Ambiguity in Query Format:** Responses often introduce ambiguity by rephrasing the original messages into questions or vague statements, which detracts from the clarity needed for effective information retrieval.**
  - See clusters (below): 25, 29, 35

- **Failure to Maintain Context:** Several responses overlook the broader context of the cardmember's request, leading to queries that do not fully address the user's needs or the specific details mentioned in their inquiries.**
  - See clusters (below): 1, 3, 18

- **Repetition of Original Messages:** Many responses simply repeat the cardmember's original message without transforming it into a more structured and actionable search query, which diminishes their effectiveness.**
  - See clusters (below): 23, 24, 34

- **Inconsistent Use of Terminology:** Some responses fail to use specific terms or phrases relevant to the inquiry, which can lead to confusion and less effective search results.**
  - See clusters (below): 1, 17, 21

<br>

## CLUSTERS: Low-Trust LLM Responses

Below we show clusters discovered amongst the subset of LLM responses that received low trustworthiness scores.

### CLUSTER 1

**Size:** 9 examples, **Average Trustworthiness Score of Cluster:** 0.515 (range: 0.067-0.763)

**Prototype Response Representing this Cluster:** view my fico score.

**Patterns detected in Cluster 1:** The low-trust responses exhibit a recurring issue of misalignment between the cardmember's original inquiry and the proposed search queries. Many responses fail to accurately reflect the specific context or intent of the cardmember's request, leading to vague or irrelevant queries. Additionally, some responses introduce ambiguity by using terms that do not clearly specify the platform or service being referenced, which can confuse the user. There is also a tendency to rephrase the cardmember's statements into questions or statements that do not maintain the original intent, resulting in less effective search queries.

**Examples from Cluster 1:**

1. **Response:** 'view my fico score.'
   **Trustworthiness Score:** 0.067

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: year summary
   AI: thank you for contacting us, [PERSON2]! your spending report helps you keep track of your finances with an interactive view of your spending by category, business, and tags. you can filter by billing period, year, and more.  {{key_[NUMBER1]}}
   Cardmember: [PERSON3]
   ````

   **Explanation:** The proposed response "view my fico score" does not accurately reflect the cardmember's original request for a "year summary." The cardmember is seeking information related to their spending report, which includes details about their finances over a specific year, rather than information about their FICO.
   This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): How can I access my spending summary for the year?

2. **Response:** 'view my fico score.'
   **Trustworthiness Score:** 0.256

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: [PERSON2]
   ````

   **Explanation:** The proposed response "view my fico score" is a self-contained query that directly addresses a specific action the cardmember may want to take regarding their credit score. It is clear and concise, making it suitable for retrieving relevant information from a FAQ Knowledge Base. The original message from the cardmember does not provide any context or specific request, but the AI Assistant's response interprets it as a request to view the FICO score, which is a common inquiry among credit card users. There is no ambiguity in the proposed response, and it aligns well with typical customer service queries related to credit.
   This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): What assistance is available for my American Express account?

3. **Response:** 'view my fico score.'
   **Trustworthiness Score:** 0.256

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: [PERSON2]
   ````

   **Explanation:** The proposed response "view my fico score" is a self-contained query that directly addresses a specific action the cardmember may want to take regarding their credit score. It is clear and concise, making it suitable for retrieving relevant information from a FAQ Knowledge Base. The original message from the cardmember does not provide any context or specific request, but the AI Assistant's response interprets it as a request to view the FICO score, which is a common inquiry among credit card users. There is no ambiguity in the proposed response, and it aligns well with typical customer service queries related to credit. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): What assistance is available for my American Express account?
<br>

**Data indices of examples in this cluster:** [43, 44, 45, 46, 47, 48, 49, 50, 51]

---

### CLUSTER 2

**Size:** 3 examples, **Average Trustworthiness Score of Cluster:** 0.194 (range: 0.115-0.256)

**Prototype Response Representing this Cluster:** thank you

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses primarily stem from a failure to address the cardmember's specific inquiries, often resulting in generic or irrelevant replies such as expressions of gratitude ("thank you" or "thanks!"). These responses do not provide the necessary information or guidance that the cardmember is seeking, which diminishes their trust in the AI's ability to assist effectively. Additionally, the responses lack clarity and specificity, leading to confusion about the actual questions posed by the cardmembers. This inconsistency in addressing user queries contributes to the overall low trustworthiness scores.

**Examples from Cluster 2:**

1. **Response:** 'thank you'
   **Trustworthiness Score:** 0.115

   **Prompt (without template):**
    ````
    Cardmember: i want to know if i need to inform american express about my upcoming travel plans.
    AI: thanks for letting us know! there's no need to notify us of your travel plans since our industry-leading fraud detection capabilities will recognize when you're traveling. your card can be used anywhere american express is accepted – even internationally. i hope you have a great trip!
    Cardmember: thank you
     ````

   **Explanation:** The proposed response "thank you" does not address the user's initial inquiry about whether they need to inform American Express about their upcoming travel plans. The user is seeking specific information regarding travel notifications, which is a verifiable fact that can be found in a FAQ Knowledge Base. The AI's response to the user's question was informative and relevant, indicating that there is no need to notify American Express about travel plans due to their fraud detection capabilities. Therefore, the search query should focus on the user's original question about notifying American Express for travel plans rather than the follow-up expression of gratitude. A more appropriate search query would be: "Do I need to inform American Express about my upcoming travel plans?" This would effectively retrieve the relevant information from the FAQ Knowledge Base. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "Is it necessary to inform American Express about my upcoming travel plans?".

2. **Response:** 'thanks!'
   **Trustworthiness Score:** 0.213

   **Prompt (without template):**
    ````
    AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
    Cardmember: traveling
    AI: thanks! no other action is required to travel with us. some good news – for your convenience, there's no need to notify us of your travel plans since our industry-leading fraud detection capabilities will recognize when you're traveling.   your card can be used anywhere american express is accepted – even internationally. i hope you have a great trip!
    Cardmember: thanks!
     ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): traveling.

3. **Response:** 'thank you!'
   **Trustworthiness Score:** 0.256

   **Prompt (without template):**
    ````
    AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
    Cardmember: hi -
    AI: hi [PERSON2], please tell me in a few words how i can help you.
    Cardmember: how do i update my password on this profile
    AI: happy to help! to change your password, log out of the app and tap 'forgot password?' enter your card details. remember, never share your login details and avoid using personal or easy-to-guess information to keep your account secure.
    Cardmember: thanks.
    AI: you're welcome!
    Cardmember: i also need to update my email address.
    AI: it's important to us that we have accurate information for you, so if your phone number, email, or home address changes, please update your information accordingly within the app. {{key_[NUMBER1]}}
    Cardmember: thank you!
     ````

   **Explanation:** The cardmember's request to update their email address is a clear and specific inquiry that can be transformed into a search query. The original message, "i also need to update my email address," directly indicates the action the cardmember wishes to take. This query is self-contained and focuses on retrieving information about the process for updating an email address within the American Express profile. The proposed response "thank you!" does not address the user's request for information and is therefore not relevant to the search query needed for the FAQ Knowledge Base. The search query created captures the essence of the cardmember's request and is likely to yield useful results regarding the steps to update their email address. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): How do I update my email address on my American Express profile?

**Data indices of examples in this cluster:** [87, 88, 89]

---

### CLUSTER 3

**Size:** 13 examples, **Average Trustworthiness Score of Cluster:** 0.643 (range: 0.378-0.731)

**Prototype Response Representing this Cluster:** i don't want to add a card to the account.

**Summary of Common Issues:** The low-trust responses in this cluster often lack specificity and clarity, failing to accurately capture the intent of the cardmember's original inquiry. Many responses are vague or ambiguous, introducing unnecessary questioning or misinterpreting the request, which can lead to confusion. Additionally, several responses do not provide a clear path for retrieving relevant information from the FAQ Knowledge Base, as they either directly repeat the cardmember's message or fail to articulate the specific information being sought. This results in search queries that are not self-contained or actionable.

**Examples from Cluster 3:**

1. **Response:** 'i don't want to add a card to the account.'
   **Trustworthiness Score:** 0.378

   **Prompt (without template):**
    ````
    AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
    Cardmember: hello
    AI: hi [PERSON2], how can i help you today?
    Cardmember: i am now a card on an account but i can only see my spending. how can the account change for me to see spending on both cards?
    AI: happy to help, [PERSON3]! to include a new card in your existing online account, follow the the prompts. {{key_[NUMBER1]}}
    Cardmember: i don’t want to add a card
     ````
   **Explanation:** The proposed response "I don't want to add a card to the account" does not accurately capture the essence of the cardmember's request. The cardmember is seeking information on how to view spending on both cards associated with their account, not simply stating their desire not to add a card. A more appropriate search query would focus on the cardmember's need to see spending for both cards, which indicates a request for guidance on account settings or features. The original message contains the necessary context and intent, making it suitable for a search query. Therefore, the proposed response fails to address the actual inquiry and does not provide a path to retrieve relevant information from the FAQ Knowledge Base. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): How can I change my account settings to view spending for both cards on my American Express account?

2. **Response:** 'provide my card number.'
   **Trustworthiness Score:** 0.553

   **Prompt (without template):**
    ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: card number
     ````
    
   **Explanation:** The proposed response "provide my card number" is a direct interpretation of the cardmember's request for "card number." However, it is important to note that the original message does not specify whether the cardmember is asking for information on how to find their card number, how to retrieve it, or if they are requesting the card number itself. Since the request is vague and could imply different needs, the proposed response does not fully encapsulate the potential intent behind the cardmember's message. A more effective search query would clarify the specific information the cardmember is seeking, such as "How can I find my American Express card number?" This would ensure that the search retrieves relevant information from the FAQ Knowledge Base. Therefore, the proposed response is not entirely s it lacks clarity and specificity.

3. **Response:** 'card verification?'
   **Trustworthiness Score:** 0.615

   **Prompt (without template):**
    ````
    Cardmember: card verification
     ````

   **Explanation:** The proposed response "card verification?" is a rephrased version of the original message "card verification." However, it introduces ambiguity by adding a question mark, which implies uncertainty or a request for confirmation rather than a straightforward search query. A more effective search query would be a direct statement or question that clearly indicates the information being sought. For instance, a better search query could be "How to verify my card?" or "What is the process for card verification?" These alternatives eliminate ambiguity and provide a clearer direction for retrieving relevant information from the FAQ Knowledge Base. Therefore, the proposed response does not adequately serve as a self-contained search query.

**Data indices of examples in this cluster:** [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]

---

### CLUSTER 4

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.314 (range: 0.218-0.409)

**Prototype Response Representing this Cluster:** question about hysa

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a tendency towards ambiguity and lack of specificity, which undermines their effectiveness as search queries. For instance, the use of acronyms like "HYSA" without context can confuse users who may not be familiar with the terminology, leading to misinterpretation of their inquiries. Additionally, the responses fail to capture the specific information the cardmembers are seeking, such as account features or management details, resulting in vague queries that are unlikely to yield useful results from a knowledge base. Overall, these responses demonstrate a lack of clarity and focus, which diminishes their reliability.

**Examples from Cluster 4:**

1. **Response:** 'question about hysa'
   **Trustworthiness Score:** 0.218

   **Prompt (without template):**
    ````
    Cardmember: question about american express savings account
     ````

   **Explanation:** The original message from the cardmember, "question about american express savings account," is a clear and self-contained query that indicates the user is seeking information specifically about American Express savings accounts. The proposed response, "question about hysa," introduces ambiguity by using an acronym (HYSA) that may not be universally understood without context. While HYSA stands for High Yield Savings Account, it does not directly address the user's inquiry about American Express savings accounts specifically. Therefore, the proposed response does not accurately reflect the user's request and could lead to confusion or misinterpretation. A better response would maintain the focus on American Express savings accounts without introducing unrelated terminology. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): American Express savings account information.

2. **Response:** 'about your hysa?'
   **Trustworthiness Score:** 0.409

   **Prompt (without template):**
    ````
    Cardmember: about my hysa
     ````

   **Explanation:** The proposed response "about your hysa?" is not a suitable search query for retrieving relevant information from a FAQ Knowledge Base. The original message "about my hysa" is vague and does not specify what information the cardmember is seeking regarding their high-yield savings account (HYSA). A more effective search query would clearly indicate the specific aspect of the HYSA the cardmember is inquiring about, such as interest rates, account features, withdrawal limits, or account management. The ambiguity in the original message means that the proposed response does not adequately capture the intent of the cardmember's request, making it less likely to yield useful results from a knowledge base. Therefore, a better search query could be "What are the features of my high-yield savings account?" or "How do I manage my high-yield savings account. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): search query: "information about my high yield savings account (HYSA)".

**Data indices of examples in this cluster:** [115, 116]

---

### CLUSTER 5

**Size:** 6 examples, **Average Trustworthiness Score of Cluster:** 0.634 (range: 0.291-0.747)

**Prototype Response Representing this Cluster:** i have not qualified for balance transfer offers.

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses often lack clarity and specificity, failing to accurately reflect the cardmember's original inquiry. Many responses introduce unnecessary wording or ambiguity, which detracts from the straightforward nature of the cardmember's requests. Additionally, several responses are phrased as questions rather than direct search queries, making them less effective for retrieving specific information from a FAQ Knowledge Base. Overall, the responses tend to dilute the original intent of the cardmember's messages, leading to potential confusion.

**Examples from Cluster 5:**

1. **Response:** 'i have not qualified for balance transfer offers.'
   **Trustworthiness Score:** 0.291

   **Prompt (without template):**
    ````
    AI: hi [NAME1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
    Cardmember: balance
    AI: ok, got it. happy to help with that. view your balance, manage payments, and more all in one place. {{key_[NUMBER1]}}
cardmember: good morning i am showing a balance on my card and i did a balance transfer that shows up on my new card but amex still shows a balance on it
AI: to see if you qualify for balance transfer offers, check online. please be aware that green, gold, and platinum cards don't support balance transfers. {{key_[NUMBER1]}}", 'ai: processing times for balance transfers are typically [NUMBER2]-[NUMBER3] days, but may take up to [NUMBER4] weeks.
Cardmember: no

   **Explanation:** The proposed response "I have not qualified for balance transfer offers" does not accurately reflect the cardmember's inquiry. The cardmember's message indicates confusion regarding a balance showing on their card after a balance transfer, rather than a statement about their qualification for balance transfer offers. The cardmember is seeking clarification on why there is still a balance on their card despite having completed a balance transfer. Therefore, the response does not address the specific concern raised by the cardmember and could lead to further confusion. A more appropriate search query would focus on understanding the status of the balance after a transfer, such as "Why does my American Express card still show a balance after a balance transfer?" This would directly relate to the cardmember's issue and help retrieve relevant information from the FAQ Knowledge Base. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "Why does my American Express card still show a balance after I completed a balance transfer?".

2. **Response:** 'inquire about the transfer balance offer.'
   **Trustworthiness Score:** 0.663

   **Prompt (without template):**
    ````
    Cardmember: credit line increased
    AI: if you’d like a higher credit limit, you can submit a request for an increase. {{key_[NUMBER1]}}
    Cardmember: transfer balance offer
     ````
    
   **Explanation:** The proposed response "inquire about the transfer balance offer" is a rephrasing of the cardmember's original message "transfer balance offer." However, it does not maintain the same clarity and directness as the original request. The original message is a straightforward request for information about a specific offer, while the proposed response introduces ambiguity by using the word "inquire," which suggests a more general action rather than a specific request for information. A better response would directly reflect the cardmember's intent to seek information about the transfer balance offer without altering the original meaning. Therefore, the proposed response is not an accurate representation of the cardmember's request.

3. **Response:** 'inquire about balance transfer.'
   **Trustworthiness Score:** 0.694

   **Prompt (without template):**
    ````
    AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
    Cardmember: balance transfer
     ````

   **Explanation:** The cardmember's message "balance transfer" is a clear and concise request for information regarding balance transfers. It does not require any additional context or elaboration to be understood as a search query. The proposed response "inquire about balance transfer" is somewhat redundant, as it adds unnecessary wording without enhancing the clarity or specificity of the original request. A more effective search query would simply be "balance transfer," which directly reflects the cardmember's inquiry. Therefore, while the proposed response is not incorrect, it is not the most efficient or straightforward representation of the cardmember's request.

**Data indices of examples in this cluster:** [21, 22, 23, 24, 25, 26]

---

### CLUSTER 6

**Size:** 4 examples, **Average Trustworthiness Score of Cluster:** 0.600 (range: 0.551-0.617)

**Prototype Response Representing this Cluster:** use atm

1. The common issue observed in the low-trust responses is the lack of specificity and clarity in the search queries derived from the cardmember's messages. The responses consistently fail to expand on the vague term "atm," which does not provide enough context for the chatbot to retrieve relevant information from the FAQ Knowledge Base. This results in generic responses like "use atm," which do not address the potential variety of inquiries a cardmember might have regarding ATMs, such as locating one, understanding fees, or troubleshooting issues. The repetitive nature of these responses indicates a need for more nuanced interpretation of user intent.

2. To avoid these patterns in the future, the original prompt could be modified to include a requirement for the AI to ask clarifying questions if the cardmember's message is too vague. Additionally, the prompt could specify that the search query should include potential variations of the user's request, encouraging the AI to generate more comprehensive and contextually relevant queries.

**Examples from Cluster 6:**

1. **Response:** 'use atm'
   **Trustworthiness Score:** 0.551

   **Prompt (without template):**
    ````
    AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
    Cardmember: atm
     ````

   **Explanation:** The cardmember's message "atm" is a very brief and somewhat ambiguous request. While it does indicate a topic of interest, it lacks specificity regarding what information the cardmember is seeking about ATMs. For example, they could be looking for information on how to find an ATM, fees associated with ATM withdrawals, or how to use an ATM. The proposed response "use atm" does not clarify the request or provide a complete search query that could yield useful results from a FAQ Knowledge Base. A better response would be to expand on the term "atm" to include specific queries such as "how to find an ATM," "ATM withdrawal limits," or "ATM fees." Therefore, the proposed response does not adequately address the user's needs. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
** How can I find an ATM and what fees are associated with using it?

2. **Response:** 'use atm'
   **Trustworthiness Score:** 0.617

   **Prompt (without template):**
    ````
    AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
    Cardmember: atm
     ````

   **Explanation:** The cardmember's message "atm" is quite vague and does not provide enough context to determine what specific information or assistance they are seeking regarding ATMs. It could refer to a variety of topics such as locating an ATM, understanding ATM fees, or issues with using an ATM. The proposed response "use atm" does not clarify the user's intent or provide a comprehensive search query that could yield relevant results from a FAQ Knowledge Base. A better search query would be more specific, such as "how to find an ATM" or "ATM fees for American Express cardholders." Therefore, the proposed response does not effectively address the user's needs.

3. **Response:** 'use atm'
   **Trustworthiness Score:** 0.617

   **Prompt (without template):**
    ````
    AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
    Cardmember: atm
     ````

   **Explanation:** The cardmember's message "atm" is quite vague and does not provide enough context to determine what specific information or assistance they are seeking regarding ATMs. It could refer to a variety of topics such as locating an ATM, understanding ATM fees, or issues with using an ATM. The proposed response "use atm" does not clarify the user's intent or provide a comprehensive search query that could yield relevant results from a FAQ Knowledge Base. A better search query would be more specific, such as "how to find an ATM" or "ATM fees for American Express cardholders." Therefore, the proposed response does not effectively address the user's needs.

**Data indices of examples in this cluster:** [52, 53, 54, 55]

---

### CLUSTER 7

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.473 (range: 0.388-0.559)

**Prototype Response Representing this Cluster:** 
original message: okay thanks
refined question: okay thanks

**Patterns detected in this cluster:** The low-trust responses in this cluster exhibit a lack of specificity and relevance to the task of creating a search query. Both examples consist of conversational phrases that do not pose a clear question or request for information, making them unsuitable for retrieval from a FAQ Knowledge Base. The responses fail to transform the original messages into actionable queries, indicating a disconnect between the cardmember's expressions of gratitude or acknowledgment and the need for information-seeking behavior. Additionally, the responses demonstrate inconsistency in how the model interprets the need for refinement, leading to confusion about what constitutes a valid search query.

**Examples from Cluster 7:**

1. **Response:** 
original message: okay thanks
refined question: okay thanks

   **Trustworthiness Score:** 0.388

   **Prompt (without template):**
   ````
   Cardmember: okay thanks
   ````

   **Explanation:** The cardmember's message "okay thanks" does not contain a specific question or request for information. It appears to be a response to a previous interaction rather than a query that seeks verifiable facts or information. Since it does not provide any context or detail that would allow for a search in a FAQ Knowledge Base, it is not suitable as a search query. Therefore, the proposed response does not improve upon the original message, as it remains unchanged and does not serve the purpose of retrieving relevant information. A better response would involve rephrasing or expanding the message to include a specific question or topic of interest related to American Express services. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
Certainly! Please provide the customer support chat message or the cardmember's inquiry that you would like to be transformed into a search query.

2. **Response:**
   original message: thank you! that worked. have a good day.
   refined question: none
   
   **Trustworthiness Score:** 0.559

   **Prompt (without template):**
   ````
   Cardmember: thank you! that worked. have a good day.
   ````

   **Explanation:** The cardmember's message is a simple expression of gratitude and does not contain a specific question or request for information that would require a search query. It is a conversational response indicating that a previous interaction was successful. Since the message does not seek verifiable facts or information, it does not need to be refined into a search query. Therefore, the proposed response correctly identifies that there is no need for a refined question. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): Search query: "What solutions are available if I encounter issues with my American Express account?".

**Data indices of examples in this cluster:** [125, 126]

---

### CLUSTER 8

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.538 (range: 0.414-0.662)

**Prototype Response Representing this Cluster:** changing your apr?

In the low-trust responses analyzed, a common issue is the lack of specificity and clarity in the proposed search queries. The responses often repeat the cardmember's original message without rephrasing it into a more structured and informative query that aligns with typical FAQ phrasing. This results in queries that may not effectively guide the search process, as they do not clearly articulate the user's intent or the context of their inquiry. Additionally, the responses exhibit inconsistency, with some being overly vague or redundant, which diminishes their trustworthiness.

To improve the quality of search queries in the future, the original prompt could be modified to emphasize the need for clarity and specificity in phrasing. For example, it could instruct the AI to rephrase the cardmember's message into a question format that directly addresses the user's intent, such as "What steps can I take to lower my APR?" This would encourage the generation of more effective and relevant search queries. Additionally, including examples of high-quality search queries could serve as a reference for the AI, helping to standardize the expected output.

**Examples from Cluster 8:**

1. **Response:** 'changing your apr?'
   **Trustworthiness Score:** 0.414

   **Prompt (without template):**
   ````
   Cardmember: changing my a p r
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
changing my a p r.

2. **Response:** 'see if i could get a lower apr.'
   **Trustworthiness Score:** 0.662

   **Prompt (without template):**
   ````
   Cardmember: see if i could get a lower a p r
   ````

   **Explanation:** The proposed response "see if i could get a lower apr" is a direct repetition of the cardmember's original message. While it does reflect the user's intent to inquire about the possibility of obtaining a lower annual percentage rate (APR), it lacks specificity and clarity that would be beneficial for a search query. A more effective search query would explicitly state the user's request in a way that aligns with common phrasing used in FAQ databases. For example, a better search query could be "How can I request a lower APR on my American Express card?" This version is more likely to yield relevant results from a knowledge base, as it clearly indicates the action the user wants to take and the context of their inquiry. Therefore, the proposed response does not meet the criteria for a high-quality search query. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
see if i could get a lower a p r.

**Data indices of examples in this cluster:** [101, 102]

---

### CLUSTER 9

**Size:** 7 examples, **Average Trustworthiness Score of Cluster:** 0.691 (range: 0.584-0.750)

**Prototype Response Representing this Cluster:** balance inquiry on a gift card?

**Summary of Common Issues:**
The low-trust responses in this cluster often suffer from a lack of specificity and clarity, which diminishes their effectiveness as search queries. Many responses rephrase the original requests into question formats or vague statements, which can lead to ambiguity and less relevant search results. Additionally, important details, such as the specific type of gift card (e.g., American Express), are frequently omitted, which is crucial for retrieving accurate information from a FAQ Knowledge Base. Overall, the responses tend to dilute the original intent of the queries, making them less suitable for effective information retrieval.

**Examples from Cluster 9:**

1. **Response:** 'balance inquiry on a gift card?'
   **Trustworthiness Score:** 0.584

   **Prompt (without template):**
    ````
    Cardmember: balance on a gift card
    ````

   **Explanation:** The proposed response "balance inquiry on a gift card?" is a rephrased version of the original request "balance on a gift card." While it captures the essence of the inquiry, it introduces a slight ambiguity by framing it as a question rather than a straightforward search query. A more effective search query would be a direct statement that clearly indicates the user is looking for information about the balance on a gift card. For example, "how to check the balance on a gift card" or "gift card balance inquiry" would be more precise and likely yield better results in a FAQ Knowledge Base. The original request is already a clear and self-contained query, so it could be left as is. Therefore, the proposed response does not fully meet the criteria for a high-quality search query.

2. **Response:** 'how can i find out what the balance is on a gift card?'
   **Trustworthiness Score:** 0.621

   **Prompt (without template):**
   ````
   AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
   Cardmember: how can i find out what the balance is on an american express gift card?
   ````

   **Explanation:** The proposed response "how can I find out what the balance is on a gift card?" is a rephrased version of the cardmember's original query. However, it lacks specificity regarding the type of gift card in question. The original message clearly specifies "an American Express gift card," which is crucial for retrieving accurate information from the FAQ Knowledge Base. The proposed response could lead to results that are not tailored to American Express gift cards specifically, potentially causing confusion for the user. A more precise search query would maintain the reference to "American Express gift card" to ensure that the information retrieved is relevant and accurate. Therefore, the proposed response is not entirely s it does not fully capture the specificity of the original request.

3. **Response:** 'looking to buy a gift card for a friend.'
   **Trustworthiness Score:** 0.694

   **Prompt (without template):**
   ````
   AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
   Cardmember: looking to buy an amex gift card for a friend
   ````

   **Explanation:** The proposed response "looking to buy a gift card for a friend" is a simplified version of the original query. However, it lacks specificity regarding the type of gift card the cardmember is interested in, which is an American Express gift card. The original message clearly states the intent to purchase an "amex gift card," which is crucial for retrieving accurate information from a FAQ Knowledge Base. The search query should maintain the specific context of the request to ensure that the chatbot can provide relevant information about purchasing an American Express gift card. Therefore, a more accurate search query would be "how to buy an American Express gift card for a friend." This revised query retains the original intent while ensuring clarity and specificity.

**Data indices of examples in this cluster:** [58, 59, 60, 61, 62, 63, 64]

---

### CLUSTER 10

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.555 (range: 0.456-0.654)

**Prototype Response Representing this Cluster:** scraa

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in Cluster 34 exhibit a lack of coherence and relevance, as they consist of nonsensical strings of characters rather than meaningful queries. Both examples fail to encapsulate the customer's intent or provide specific context, which is essential for retrieving accurate information from a FAQ Knowledge Base. Additionally, the responses do not demonstrate an understanding of the subject matter, as seen in the vague reference to the Servicemembers Civil Relief Act (SCRA) without sufficient detail. Overall, these responses highlight a significant gap in clarity and specificity, which undermines their effectiveness as search queries.

**Examples from Cluster 10:**

1. **Response:** 'scraa'
   **Trustworthiness Score:** 0.456

   **Prompt (without template):**
   ````
   cardmember: [PERSON1]
   ````

   **Explanation:** The proposed response "scraa" does not represent a coherent or relevant search query that could be used to retrieve information from a FAQ Knowledge Base. It appears to be a random string of characters rather than a meaningful question or statement related to American Express customer service. A proper search query should encapsulate the customer's intent or specific question regarding their account, services, or any issues they may be facing. Since the original message from the cardmember is not provided, it is impossible to determine if it was already a self-contained query. However, based on the response given, it is clear that it does not meet the criteria for a valid search query. Therefore, the proposed response is incorrect. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
cardmember: "What are the benefits of using my American Express card for travel purchases?"
search query: "What are the benefits of using an American Express card for travel purchases?".

2. **Response:** 'scra'
   **Trustworthiness Score:** 0.654

   **Prompt (without template):**
   ````
   cardmember: [PERSON1]
   ````

   **Explanation:** The proposed response "scra" is not a self-contained search query that would effectively retrieve relevant information from a FAQ Knowledge Base. The term "scra" likely refers to the Servicemembers Civil Relief Act, but it lacks context and specificity. A better search query would include more detail, such as "What is the Servicemembers Civil Relief Act (SCRA) benefits for American Express cardmembers?" This would provide clearer guidance for the search process and ensure that the information retrieved is directly relevant to the cardmember's needs. The original message from the cardmember does not appear in the provided text, making it difficult to assess the intent behind the query. However, based on the information given, the response does not meet the criteria for a high-quality search query.

**Data indices of examples in this cluster:** [113, 114]

---

### CLUSTER 11

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.593 (range: 0.593-0.593)

**Prototype Response Representing this Cluster:** linking which account?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a pattern of unnecessary clarification that undermines the clarity of the original user queries. Both responses attempt to ask for more specific information ("linking which account?" and "link which account?") when the original messages ("linking an account" and "link an account") are already clear and self-contained. This introduces ambiguity and does not enhance the user's request for information, leading to a lack of trust in the responses. The responses fail to recognize that the user's intent is straightforward and can be directly addressed without further questioning.

**Examples from Cluster 11:**

1. **Response:** 'linking which account?'
   **Trustworthiness Score:** 0.593

   **Prompt (without template):**
   ````
   Cardmember: linking an account
   ````

   **Explanation:** The proposed response "linking which account?" is an attempt to clarify the user's request by asking for more specific information. However, the original message "linking an account" is already a self-contained query that indicates the user is seeking information about the process of linking an account. The response does not add value and instead introduces ambiguity by asking for clarification when the original request is straightforward. A better response would simply be to use the original message as the search query, as it directly addresses the user's intent without requiring further information. Therefore, the proposed response is not appropriate in this context.

2. **Response:** 'link which account?'
   **Trustworthiness Score:** 0.593

   **Prompt (without template):**
   ````
   Cardmember: link an account
   ````

   **Explanation:** The proposed response "link which account?" is an attempt to clarify the user's request but does not serve as a self-contained search query. The original message "link an account" is already a clear and concise request that can be used to retrieve relevant information from a FAQ Knowledge Base. The user is likely looking for instructions or information on how to link an account, which is a specific action. The proposed response introduces ambiguity by asking for clarification instead of directly addressing the user's request. Therefore, the original message should be used as the search query without modification. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
How to link an account with American Express?

**Data indices of examples in this cluster:** [111, 112]

---

### CLUSTER 12

**Size:** 4 examples, **Average Trustworthiness Score of Cluster:** 0.674 (range: 0.651-0.693)

**Prototype Response Representing this Cluster:** what is my question about a fee?

The common issues observed in the low-trust responses include a lack of specificity and clarity in the proposed search queries. Many responses rephrase the cardmember's original messages without enhancing their context or detail, leading to vague queries that do not effectively guide the search process. Additionally, some responses frame the inquiry as a question rather than a direct search query, which can hinder the retrieval of relevant information from the FAQ Knowledge Base. Overall, the responses fail to capture the cardmember's intent accurately, resulting in queries that are not self-contained or actionable.

To avoid these patterns in the future, the original prompt could be modified to emphasize the importance of specificity and context in the search queries. Additionally, including examples of high-quality search queries that effectively capture the cardmember's intent could serve as a guide for generating more precise and actionable responses.

**Examples from Cluster 12:**

1. **Response:** 'what is my question about a fee?'
   **Trustworthiness Score:** 0.651

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: hello
   AI: hi [NAME1], please tell me in a few words how i can help you.
   Cardmember: question about a fee?
   ````

   **Explanation:** The proposed response "what is my question about a fee?" does not accurately reflect the cardmember's original message, which is simply "question about a fee?" This original message indicates that the cardmember has a specific inquiry regarding a fee but does not provide enough context to formulate a precise question. The proposed response implies that the chatbot is asking the cardmember to clarify their question, which is not necessary. A more appropriate search query would directly reflect the cardmember's intent to inquire about fees without rephrasing it as a question. A better search query could be "What fees are associated with my American Express account?" or "How can I inquire about fees on my account?" This would allow the chatbot to retrieve relevant information from the FAQ Knowledge Base without requiring further clarification from the cardmember.

2. **Response:** 'regarding which fees are you inquiring about?'
   **Trustworthiness Score:** 0.661

   **Prompt (without template):**
   ````
   Cardmember: regarding fees
   ````

   **Explanation:** The proposed response "regarding which fees are you inquiring about?" is an attempt to clarify the cardmember's request, but it does not serve as a self-contained search query. The original message "regarding fees" is vague and does not specify which fees the cardmember is referring to, such as annual fees, late payment fees, foreign transaction fees, etc. However, the task requires creating a search query that can directly retrieve relevant information from a FAQ Knowledge Base. A more effective search query would be "What fees are associated with American Express cards?" This query is specific enough to yield relevant results while still addressing the cardmember's inquiry about fees. Therefore, the proposed response does not meet the requirement of being a self-contained search query.

3. **Response:** 'incorrect fee?'
   **Trustworthiness Score:** 0.688

   **Prompt (without template):** cardmember: incorrect fee

   **Explanation:** The proposed response "incorrect fee?" is not a suitable search query for retrieving relevant information from a FAQ Knowledge Base. While it does reflect the cardmember's concern about an incorrect fee, it is phrased as a question rather than a clear search query. A more effective search query would be a direct statement that encapsulates the issue, such as "how to dispute an incorrect fee" or "what to do about an incorrect fee on my account." This would provide a more focused and actionable search term that could lead to specific answers in the knowledge base. The original message "incorrect fee" is already a concise statement of the issue, but it lacks the context needed for a search engine to retrieve relevant information effectively. Therefore, the proposed response does not meet the criteria for a high-quality search query.

**Data indices of examples in this cluster:** [65, 66, 67, 68]

---

### CLUSTER 13

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.609 (range: 0.606-0.612)

**Prototype Response Representing this Cluster:** account amount owed?

**Summary of Common Issues in Low-Trust Responses:**
The low-trust responses in this cluster exhibit a lack of clarity and specificity, which hinders their effectiveness as search queries. Both examples attempt to rephrase the original messages but introduce ambiguity, making it difficult for a search process to retrieve relevant information. The responses also fail to maintain the straightforward nature of the original queries, which are already clear requests for information. Overall, the proposed responses do not align well with the expected format for a knowledge base search, leading to lower trustworthiness scores.

**Examples from Cluster 13:**

1. **Response:** 'account amount owed?'
   **Trustworthiness Score:** 0.606

   **Prompt (without template):**
   ````
   Cardmember:  acct amount owed
   ````

   **Explanation:** The proposed response "account amount owed?" is a rephrased version of the original message "acct amount owed," which is a request for information about the amount owed on the account. However, the rephrased query lacks clarity and specificity. The original message is already a straightforward request for information regarding the account balance, and it can be directly used as a search query without modification. The proposed response introduces ambiguity by changing "acct" to "account" and framing it as a question, which may not align with the format of the knowledge base. A better response would simply be "acct amount owed" or "amount owed on my account," as these are clear and direct queries that can effectively retrieve the relevant information from the FAQ Knowledge Base. Therefore, the proposed response is not the best option.

2. **Response:** 'account amount?'
   **Trustworthiness Score:** 0.612

   **Prompt (without template):**
   ````
   Cardmember:  account amount
   ````

   **Explanation:** The proposed response "account amount?" is not a self-contained search query. It lacks clarity and specificity, making it difficult for a search process to retrieve relevant information. The original message "account amount" suggests that the cardmember is likely inquiring about the balance or total amount available in their account, but the proposed response does not explicitly convey this intent. A better search query would be something like "What is my account balance?" or "How can I check my account amount?" which clearly indicates the user's need for information regarding their account balance. The ambiguity in the original message could lead to varied interpretations, and the proposed response does not effectively address the user's request for information. Therefore, the proposed response is incorrect.

**Data indices of examples in this cluster:** [13, 14]

---

### CLUSTER 14

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.616 (range: 0.507-0.726)

**Prototype Response Representing this Cluster:** statement closing date of your credit card?

In the low-trust responses analyzed, a common issue is the unnecessary rephrasing of the original customer queries, which often leads to ambiguity and a lack of clarity. For instance, the first response introduces extraneous wording that does not enhance the searchability of the query, while the second response conflates two distinct inquiries, resulting in a confusing search query. Both examples demonstrate a failure to maintain the original intent and specificity of the cardmember's questions, which is crucial for effective information retrieval from a knowledge base.

To avoid these patterns in the future, the original prompt could be modified to emphasize the importance of retaining the original query's clarity and intent. Additionally, it could specify that responses should focus solely on the most relevant aspect of the customer's inquiry, avoiding any unnecessary elaboration or merging of topics. This would help ensure that the generated search queries are both concise and directly aligned with the customer's needs.

**Examples from Cluster 14:**

1. **Response:** 'statement closing date of your credit card?'
   **Trustworthiness Score:** 0.507

   **Prompt (without template):**
   ````
   Cardmember: statement closing date of my cc
   ````

   **Explanation:** The proposed response "statement closing date of your credit card?" is a rephrasing of the original query but does not function as a self-contained search query. A self-contained search query should be a direct statement or question that can be used to retrieve specific information from a knowledge base. The original message "statement closing date of my cc" is already a concise and clear request for information regarding the closing date of the credit card statement. Therefore, it is appropriate as a search query without needing rephrasing. The proposed response introduces unnecessary wording and changes the structure, which could lead to ambiguity in search results. A better response would simply be to retain the original message as it is already suitable for searching. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): What is the statement closing date of my credit card?

2. **Response:** 'i want to know my chip and signature/pin card's billing cycle closing date.'
   **Trustworthiness Score:** 0.726

   **Prompt (without template):**
   ````
   Cardmember: i have a question about my chip and signature/pin card
   AI: chip technology adds extra security to your transactions. find out more about how and where you can use your chip card. {{key_[NUMBER1]}}
   Cardmember: i want to know my billing cycle closing date
   ````

   **Explanation:** The proposed response is incorrect because it combines two separate inquiries from the customer support chat. The cardmember initially asked about their chip and signature/PIN card, but the follow-up question specifically pertains to their billing cycle closing date. The proposed response incorrectly merges these two topics, which could lead to confusion when searching for relevant information. A better search query would focus solely on the billing cycle closing date without referencing the chip and signature/PIN card, as the cardmember's intent is clear in their second message. Therefore, the correct search query should simply be "What is my billing cycle closing date?" to ensure clarity and relevance in retrieving the appropriate information from the FAQ Knowledge Base.

**Data indices of examples in this cluster:** [56, 57]

---

### CLUSTER 15

**Size:** 3 examples, **Average Trustworthiness Score of Cluster:** 0.668 (range: 0.471-0.767)

**Prototype Response Representing this Cluster:** not a pdf copy of the statement

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a lack of specificity and clarity, which hinders their effectiveness as search queries. For instance, the first response is a direct repetition of the cardmember's message without any additional context, making it unhelpful for retrieving relevant information. The other two responses, while self-contained, fail to specify the exact nature of the inquiry regarding statement PDFs, leading to ambiguity that could result in less targeted search results. Overall, these responses demonstrate a need for more detailed and precise queries to enhance their trustworthiness and utility.

**Examples from Cluster 15:**

1. **Response:** 'not a pdf copy of the statement'
   **Trustworthiness Score:** 0.471

   **Prompt (without template):**
   ````
   Cardmember: not a pdf copy of statement
   ````

   **Explanation:** The proposed response "not a pdf copy of the statement" is a direct repetition of the cardmember's message and does not provide a clear search query that could effectively retrieve relevant information from a FAQ Knowledge Base. A more effective search query would specify the type of statement the cardmember is looking for, such as "how to obtain a PDF copy of my statement" or "options for receiving my statement." The original message lacks clarity and context, making it difficult for a search engine to understand the specific information the cardmember is seeking. Therefore, the proposed response does not meet the criteria for a self-contained search query. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): How to obtain a PDF copy of my American Express statement?

2. **Response:** 'i have a question about my statement pdfs.'
   **Trustworthiness Score:** 0.767

   **Prompt (without template):**
   ````
   Cardmember: i have a question about my statement pdfs
   ````

   **Explanation:** The proposed response "i have a question about my statement pdfs" is indeed a self-contained query that reflects the cardmember's request for information regarding their statement PDFs. However, it lacks specificity and does not clearly indicate what aspect of the statement PDFs the cardmember is inquiring about. A more effective search query would specify whether the cardmember is looking for how to access, download, or understand their statement PDFs. The ambiguity in the original message could lead to a less targeted search result, as it does not clarify the exact nature of the question. Therefore, while the response is technically correct, it could be improved for clarity and specificity.

3. **Response:** 'i have a question about my statement pdfs.'
   **Trustworthiness Score:** 0.767

   **Prompt (without template):**
   ````
   Cardmember: i have a question about my statement pdfs
   ````

   **Explanation:** The proposed response "i have a question about my statement pdfs" is indeed a self-contained query that reflects the cardmember's request for information regarding their statement PDFs. However, it lacks specificity and does not clearly indicate what aspect of the statement PDFs the cardmember is inquiring about. A more effective search query would specify whether the cardmember is looking for how to access, download, or understand their statement PDFs. The ambiguity in the original message could lead to a less targeted search result, as it does not clarify the exact nature of the question. Therefore, while the response is technically correct, it could be improved for clarity and specificity.

**Data indices of examples in this cluster:** [40, 41, 42]

---

### CLUSTER 16

**Size:** 3 examples, **Average Trustworthiness Score of Cluster:** 0.671 (range: 0.567-0.748)

**Prototype Response Representing this Cluster:** request for credit limit increase.

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses exhibit a lack of specificity and clarity, failing to fully capture the intent of the cardmember's inquiries. Many responses are overly simplistic or vague, such as "request for credit limit increase," which does not address the user's concern about the impact on their credit score. Additionally, some responses merely rephrase the original message without enhancing the context or providing actionable information, leading to ambiguity in search results. Overall, these responses do not effectively guide the user toward retrieving relevant information from the FAQ Knowledge Base.

**Examples from Cluster 16:**

1. **Response:** 'request for credit limit increase.'
   **Trustworthiness Score:** 0.567

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: hello, will credit increase request affect negatively my credit score?
   AI: here to help! you can view your free credit score and report with mycredit guide. sign up for alerts, set goals to improve your credit score, and explore the simulator to see how your score can be affected by things like taking out a loan. {{key_[NUMBER1]}}
   Cardmember: credit limit increase
   ````

   **Explanation:** The proposed response "request for credit limit increase" is a straightforward interpretation of the cardmember's message. However, it does not fully encapsulate the essence of the cardmember's inquiry, which is about the potential impact of a credit limit increase request on their credit score. The original message explicitly asks whether such a request would negatively affect their credit score, indicating a need for information rather than just a statement about the request itself. A more accurate search query would directly address the concern about the credit score, such as "Does requesting a credit limit increase affect my credit score?" This would lead to more relevant information regarding the implications of a credit limit increase on credit. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
Will a credit limit increase request negatively affect my credit score?

2. **Response:** 'increase credit available?'
   **Trustworthiness Score:** 0.698

   **Prompt (without template):**
   ````
   Cardmember: credit available increase
   ````

   **Explanation:** The proposed response "increase credit available?" is a rephrased version of the original query "credit available increase." However, it lacks clarity and specificity. The original message indicates that the cardmember is likely seeking information on how to increase their available credit limit, which is a specific action. The proposed response, while it does imply a question about increasing credit, does not clearly convey the intent of the user to seek guidance or information on the process or eligibility for increasing their credit limit. A better search query could be "How to increase my available credit limit?" or "Steps to request a credit limit increase." These alternatives provide a clearer context for the search, making it easier to retrieve relevant information from the FAQ Knowledge Base. Therefore, the proposed response does not effectively capture the user's intent and could lead to ambiguity in search results.

4. **Response:** 'i would like to explore the possibility of raising my credit limit, please.'
   **Trustworthiness Score:** 0.748

   **Prompt (without template):**
   ````
   Cardmember: would like to explore the possibility of raising my credit limit , please .
   ````

   **Explanation:** The proposed response is a direct repetition of the cardmember's request, which is indeed a self-contained query. However, it lacks specificity and does not align with the typical format of a search query that would be used to retrieve information from a FAQ Knowledge Base. A more effective search query would focus on the key action the cardmember is interested in, such as "how to raise my credit limit" or "credit limit increase process." This would help in retrieving relevant information more efficiently. Therefore, while the proposed response is technically correct in that it reflects the user's request, it does not optimize the search for relevant information.

**Data indices of examples in this cluster:** [96, 97, 98]

---

### CLUSTER 17

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.632 (range: 0.564-0.701)

**Prototype Response Representing this Cluster:** what is your billing question?

**Patterns detected in this cluster:** The low-trust responses in this cluster exhibit a lack of specificity and clarity, which hinders their effectiveness as self-contained search queries. The first response, "what is your billing question?" is an open-ended question that fails to encapsulate the cardmember's intent, while the second response, "billing issues," is too vague and does not address the potential variety of billing-related inquiries. Both responses demonstrate a tendency to invite further elaboration rather than providing direct, actionable search queries that could retrieve relevant information from a FAQ Knowledge Base. This indicates a need for more precise language that directly reflects the cardmember's needs.

**Examples from this Cluster:**

1. **Response:** 'what is your billing question?'
   **Trustworthiness Score:** 0.564

   **Prompt (without template):**
   ````
   AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
   Cardmember: billing question
   ````

   **Explanation:** The proposed response "what is your billing question?" is not a self-contained search query that can be used to retrieve information from a FAQ Knowledge Base. Instead, it is an open-ended question that invites further elaboration from the cardmember. The original message "billing question" is a concise and clear indication of the topic the cardmember needs assistance with, making it suitable as a search query. A better search query would directly reflect the cardmember's intent to seek information about billing, such as "billing questions" or "how to resolve billing issues." Therefore, the proposed response does not meet the requirement of being a self-contained query. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "How can I get assistance with my billing questions regarding my American Express account?".

2. **Response:** 'billing issues'
   **Trustworthiness Score:** 0.701

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: is there a way for me to see my card number somewhere on this app? or on my feelings statement?
   AI: for your security, your account number can only be found on your physical card. our customer care professionals can't provide you with this information.  if your card has been lost or stolen, you can request a replacement.
   Cardmember: billing
   ````

   **Explanation:** The proposed response "billing issues" is a reasonable interpretation of the cardmember's message "billing." However, it lacks specificity and does not fully capture the potential breadth of the cardmember's inquiry. The term "billing" could refer to various topics such as billing statements, payment due dates, billing disputes, or charges on the account. A more effective search query would be something like "how to view billing statements" or "billing statement details," which would provide clearer guidance for retrieving relevant information from the FAQ Knowledge Base. The original message is indeed open-ended, but it does not provide enough context to determine the exact nature of the billing inquiry. Therefore, while the proposed response is not incorrect, it could be improved for clarity and specificity.

**Data indices of examples in this cluster:** [90, 91]

---

### CLUSTER 18

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.633 (range: 0.479-0.788)

**Prototype Response Representing this Cluster:** who are you?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a significant lack of clarity and specificity, leading to confusion about the chatbot's identity and purpose. Both examples consist of the same basic question, "who are you?", which fails to provide context or detail that would help the model generate a more informative response. Additionally, the alternate responses suggested by the model are inconsistent and do not effectively address the cardmember's inquiry, further contributing to the low trustworthiness scores. This indicates a need for more precise and contextually relevant queries to elicit better responses.

**Examples from Cluster 18:**

1. **Response:** 'who are you?'
   **Trustworthiness Score:** 0.479

   **Prompt (without template):**
   ````
   Cardmember: who are you ?
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either):  "What is the purpose of the American Express customer service chatbot?".

2. **Response:** 'who are you?'
   **Trustworthiness Score:** 0.788

   **Prompt (without template):**
   ````
   Cardmember: no name who are you ?
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "What is the identity of the customer service chatbot?".

**Data indices of examples in this cluster:** [105, 106]

---

### CLUSTER 19

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.635 (range: 0.602-0.668)

**Prototype Response Representing this Cluster:** what is my marriott bonvoy account member number?

**Patterns detected in this cluster:** The low-trust responses in Cluster 17 exhibit a lack of clarity and specificity in addressing the cardmember's needs. In the first example, the response focuses solely on retrieving the member number without acknowledging the cardmember's initial request for confirmation of the connection between their American Express card and Marriott Bonvoy account. This oversight leads to a disconnect between the user's intent and the response provided. Similarly, the second response, while actionable, does not fully capture the context of the inquiry regarding account management, which could lead to confusion. Overall, the responses reflect a tendency to isolate specific queries without considering the broader context of the cardmember's requests.

**Examples from Cluster 19:**

1. **Response:** 'what is my marriott bonvoy account member number?'
   **Trustworthiness Score:** 0.602

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: hi, can you please confirm that my marriott amex is connected to my marriott bonvoy account?
   AI: i can help with questions about marriott bonvoy™ points. select what you'd like to know more about:
   Cardmember: member number
   ````

   **Explanation:** The proposed response "what is my marriott bonvoy account member number?" is indeed a self-contained query that seeks specific information about the member number associated with the Marriott Bonvoy account. The original cardmember's message, "can you please confirm that my marriott amex is connected to my marriott bonvoy account?" indicates a need for verification of the connection between their American Express card and their Marriott Bonvoy account. However, the follow-up message "member number" suggests that the cardmember is looking for information related to their member number, which is a specific piece of information that can be retrieved from a FAQ Knowledge Base. The proposed response is appropriate as it directly addresses the cardmember's request for their member number, making it a valid search query. Therefore, the response is correct in the context of the information being sought. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "How can I confirm if my Marriott American Express card is connected to my Marriott Bonvoy account?".

2. **Response:** 'add my marriott member number to my account.'
   **Trustworthiness Score:** 0.668

   **Prompt (without template):**
   ````
   AI: hi [PERSON1], please select one of these options, or in a few words tell me what you need help with.
   Cardmember: add someone to my account
   AI: you can add additional cards or employee cards so that others can make purchases using your account. establishing an account manager allows someone else to manage account details on your behalf.   which of these would you like to do?
   Cardmember: marriott member number
   ````

   **Explanation:** The proposed response "add my marriott member number to my account" is a clear and actionable request that aligns with the cardmember's original message about needing assistance with their Marriott member number. The cardmember's inquiry is straightforward and indicates a desire to link their Marriott membership with their American Express account. The response effectively captures the essence of the request, making it suitable for a search query in a FAQ Knowledge Base. There is no ambiguity in the request, and it directly addresses the need for information on how to add a Marriott member number to their account. Therefore, the proposed response is s it accurately reflects the user's intent and can be used to retrieve relevant information. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "How can I find my Marriott member number?".

**Data indices of examples in this cluster:** [73, 74]

---

### CLUSTER 20

**Size:** 6 examples, **Average Trustworthiness Score of Cluster:** 0.712 (range: 0.646-0.774)

**Prototype Response Representing this Cluster:** what is my delta skymiles number?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses exhibit a pattern of vagueness and inconsistency, often failing to provide clear, direct queries that align with typical search engine expectations. Many responses introduce uncertainty through phrasing, such as using question marks or ambiguous language, which detracts from their effectiveness as search queries. Additionally, there is a tendency for the responses to be overly simplistic or incomplete, lacking the necessary context to retrieve specific information from a FAQ Knowledge Base. This inconsistency in response quality suggests a need for more precise and contextually relevant phrasing.

**Examples from this Cluster:**

1. **Response:** 'what is my delta skymiles number?'
   **Trustworthiness Score:** 0.646

   **Prompt (without template):**
   ````
   Cardmember: i want to redeem delta skymiles
   AI: you can redeem miles towards travel on delta and its other airline partners directly on delta.com. {{key_[NUMBER1]}}
   Cardmember: what is my skymiles
   AI: i can help with questions about your delta skymiles® card.  just let me know the topic.
   Cardmember: number
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "What is my SkyMiles balance?".

2. **Response:** 'what is my delta skymiles® number?'
   **Trustworthiness Score:** 0.665

   **Prompt (without template):**
   ````
   AI: hi [NAME1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
   Cardmember: delta sky rewards
   AI: i can help with questions about your delta skymiles® card.  just let me know the topic.
   Cardmember: redeeming miles
   AI: you can redeem miles towards travel on delta and its other airline partners directly on delta.com. {{key_[NUMBER1]}}
   Cardmember: delta sky rewards membership
   AI: i can help with questions about your delta skymiles® card.  just let me know the topic.
   Cardmember: skymiles® number
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "What is the Delta SkyMiles program and how can I redeem my SkyMiles?".

3. **Response:** 'skymiles number?'
   **Trustworthiness Score:** 0.692

   **Prompt (without template):**
   ````
   Cardmember: skymiles number
   ````

   **Explanation:** The prompt/response appear atypical or vague.

**Data indices of examples in this cluster:** [81, 82, 83, 84, 85, 86]

---

### CLUSTER 21

**Size:** 4 examples, **Average Trustworthiness Score of Cluster:** 0.705 (range: 0.632-0.758)

**Prototype Response Representing this Cluster:** i can't see how many star points i have available.

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses exhibit a tendency to either directly repeat the cardmember's message or rephrase it in a way that introduces ambiguity. Many of the proposed search queries fail to clearly specify the information being sought, leading to potential confusion about the exact nature of the inquiry. Additionally, some responses shift the focus from specific terms (like "SPG points") to more general phrases (like "points"), which dilutes the clarity and effectiveness of the search query. Overall, these responses lack the conciseness and specificity needed for high-quality search queries.

**Examples from Cluster 21:**

1. **Response:** 'i can't see how many star points i have available.'
   **Trustworthiness Score:** 0.632

   **Prompt (without template):**
   ````
   Cardmember: i can't see how many star points i have available
   ````

   **Explanation:** The proposed response is a direct repetition of the cardmember's message, which is not an ideal search query for retrieving information from a FAQ Knowledge Base. A high-quality search query should be concise and focused on the specific information the user is seeking. In this case, the cardmember is looking for information about their available star points, so a better search query would be something like "How to check available star points on my account?" This alternative query is more actionable and would likely yield more relevant results in a knowledge base. Therefore, the proposed response does not effectively serve the purpose of a search query. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): How can I check how many star points I have available?

2. **Response:** 'can you provide my spg points balance?'
   **Trustworthiness Score:** 0.683

   **Prompt (without template):**
   ````
   Cardmember: can you tell me my spg points balance
   ````

   **Explanation:** The proposed response "can you provide my spg points balance?" is a rephrased version of the original request and maintains the same intent. However, it is not a self-contained search query that can be directly used to retrieve information from a FAQ Knowledge Base. A more effective search query would be a direct question or statement that clearly indicates the information being sought, such as "What is my SPG points balance?" This version eliminates any ambiguity and directly addresses the need for information about the SPG points balance. Therefore, the proposed response does not meet the criteria for a high-quality search query.

3. **Response:** 'how can i view how many points i have in my starwood account?'
   **Trustworthiness Score:** 0.747

   **Prompt (without template):**
   ````
   Cardmember: how can i view how many starwood points i have ?
   ````

   **Explanation:** The proposed response rephrases the original query but introduces ambiguity by changing "starwood points" to "points in my starwood account." The original query specifically asks about "starwood points," which implies a direct inquiry into the points balance rather than a general inquiry about the account. The rephrased version could lead to confusion, as it may not clearly indicate that the user is specifically interested in the number of points rather than other account details. Therefore, the proposed response does not accurately capture the essence of the original question. A better response would maintain the focus on "starwood points" and directly address the inquiry about viewing the points balance.

**Data indices of examples in this cluster:** [119, 120, 121, 122]

---

### CLUSTER 22

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.675 (range: 0.664-0.685)

**Prototype Response Representing this Cluster:** what is my due date?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a lack of clarity and consistency, which undermines their effectiveness as search queries. For instance, the response "what is my due date?" is straightforward but lacks context, while "due date clarification needed?" introduces ambiguity and suggests uncertainty about the user's request. This inconsistency can lead to confusion, as the responses do not align with the user's clear intent. Additionally, the responses fail to maintain a focus on providing direct and actionable queries that can be easily matched with relevant information in a FAQ Knowledge Base.

**Examples from Cluster 22:**

1. **Response:** 'what is my due date?'
   **Trustworthiness Score:** 0.664

   **Prompt (without template):**
   ````
   AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
   Cardmember: can you help me with my account?
   AI: to better understand your needs, please share a short sentence on how i can help you today.
   Cardmember: when is my due date?
   AI: ok, got it. happy to help with that. view your balance, manage payments, and more all in one place. {{key_[NUMBER1]}}
   Cardmember: what date is it?
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): What is the current date?

2. **Response:** 'due date clarification needed?'
   **Trustworthiness Score:** 0.685

   **Prompt (without template):**
   ````
   Cardmember:  due date
   ````

   **Explanation:** The proposed response "due date clarification needed?" is not a self-contained search query. The original message "due date" is a straightforward request for information regarding the due date, likely related to payment or billing. The proposed response introduces ambiguity by suggesting that clarification is needed, which implies that the user may not be clear about what they are asking. However, the original message is already a clear and concise query that can be used to retrieve relevant information from a FAQ Knowledge Base. A better response would simply be "What is my due date?" or "Due date information." This would directly address the user's request without introducing unnecessary ambiguity. Therefore, the proposed response does not accurately reflect the user's intent and is not suitable for a search query.

**Data indices of examples in this cluster:** [17, 18]

---

### CLUSTER 23

**Size:** 3 examples, **Average Trustworthiness Score of Cluster:** 0.703 (range: 0.602-0.758)

**Prototype Response Representing this Cluster:** using points for travel?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a common issue of introducing unnecessary ambiguity by framing the original queries as questions. Each proposed response adds a question mark, which transforms a clear and direct statement into an interrogative form, potentially leading to confusion in the search process. Additionally, the original messages are already concise and self-contained, making the rephrased versions redundant and less effective for retrieving information. Overall, the lack of clarity and directness in the rephrased responses contributes to their low trustworthiness scores.

**Examples from Cluster 23:**

1. **Response:** 'using points for travel?'
   **Trustworthiness Score:** 0.602

   **Prompt (without template):**
   ````
   Cardmember: using points for travel
   ````

   **Explanation:** The proposed response "using points for travel?" is a rephrased version of the original query but does not effectively serve as a self-contained search query. A self-contained search query should be clear and direct, allowing for easy retrieval of relevant information from a FAQ Knowledge Base. The original message "using points for travel" is already concise and straightforward, making it suitable as a search query. However, the proposed response introduces a question format that may not align with the typical structure of search queries, which are often declarative rather than interrogative. A better response would simply be "using points for travel" without the question mark, as it maintains the original intent and clarity. Therefore, the proposed response is not the best option for retrieving information effectively.

2. **Response:** 'book travel using points?'
   **Trustworthiness Score:** 0.750

   **Prompt (without template):**
   ````
   Cardmember: book travel using points
   ````

   **Explanation:** The proposed response "book travel using points?" is a rephrased version of the original query but introduces unnecessary ambiguity by adding a question mark. The original message "book travel using points" is a clear and direct request for information on how to book travel using points, which is suitable for a search query. The addition of the question mark implies uncertainty and transforms it into a question rather than a straightforward search query. A better response would simply be to retain the original message as it is, as it is already self-contained and effectively communicates the user's intent. Therefore, the proposed response does not accurately reflect the clarity and directness of the original request.

3. **Response:** 'use points to travel?'
   **Trustworthiness Score:** 0.758

   **Prompt (without template):**
   ````
   Cardmember: use points to travel
   ````

   **Explanation:** The proposed response "use points to travel?" is a rephrased version of the original message but does not effectively serve as a self-contained search query. A search query should be clear and direct, allowing for easy retrieval of relevant information from a FAQ Knowledge Base. The original message "use points to travel" is already a straightforward request for information about using points for travel, making it suitable as a search query. The proposed response introduces unnecessary ambiguity by framing it as a question, which could lead to confusion in the search process. A better response would simply be "use points to travel" as it directly reflects the user's intent without altering the meaning. Therefore, the proposed response is not s it does not maintain the clarity and directness needed for an effective search query.

**Data indices of examples in this cluster:** [127, 128, 129]

---

### CLUSTER 24

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.682 (range: 0.596-0.768)

**Prototype Response Representing this Cluster:** does the card have foreign transaction fees?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a tendency to introduce ambiguity or lack specificity, which diminishes their effectiveness as search queries. In the first example, the rephrased question fails to explicitly reference American Express, leading to potential confusion about which card's policies are being inquired about. Similarly, the second response alters the phrasing in a way that broadens the context, moving away from the straightforward nature of the original question. Both responses could benefit from maintaining the original wording to ensure clarity and precision, which are crucial for effective information retrieval.

**Examples from Cluster 24**:

1. **Response:** 'does the card have foreign transaction fees?'
   **Trustworthiness Score:** 0.596

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: does amex have foreign transaction fees?
   ````

   **Explanation:** The proposed response "does the card have foreign transaction fees?" is a rephrased version of the cardmember's original question, "does amex have foreign transaction fees?" While it maintains the essence of the inquiry, it lacks specificity regarding American Express (Amex) as a company. The original question clearly asks about Amex's policies, while the proposed response could be interpreted as asking about any card in general, which may lead to ambiguity. A more precise search query would directly reference American Express to ensure that the information retrieved pertains specifically to their policies. Therefore, the proposed response is not entirely s it does not fully capture the context of the original question.

2. **Response:** 'is there a fee for charging currency exchange with my card?'
   **Trustworthiness Score:** 0.768

   **Prompt (without template):**
   ````
   Cardmember: is there a fee for charging currency exchange with my amex card
   ````

   **Explanation:** The proposed response is a rephrased version of the original query, which retains the essential elements of the customer's question about fees associated with currency exchange when using their American Express card. However, it introduces slight ambiguity by changing "charging currency exchange" to "charging currency exchange with my card," which could imply a broader context than the original question. The original query is straightforward and directly asks about the existence of a fee, making it a clear and self-contained search query. A better response would maintain the original phrasing to avoid any potential confusion. Therefore, while the proposed response is not entirely incorrect, it could be improved for clarity and precision.

**Data indices of examples in this cluster:** [79, 80]

---

### CLUSTER 25

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.690 (range: 0.637-0.744)

**Prototype Response Representing this Cluster:** help adding additional employee cards?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a tendency to introduce question formats that create ambiguity, detracting from the clarity needed for effective search queries. Both examples rephrase the original requests into questions, which can imply uncertainty rather than a straightforward request for information. This shift in tone may lead to confusion in retrieving relevant answers from a FAQ Knowledge Base. Additionally, the original messages are already clear and self-contained, indicating that the rephrased versions are unnecessary and less effective for the intended purpose.

**Examples from Cluster 25:**

1. **Response:** 'help adding additional employee cards?'
   **Trustworthiness Score:** 0.637

   **Prompt (without template):**
   ````
   Cardmember: help adding additional employee cards
   ````

   **Explanation:** The proposed response "help adding additional employee cards?" is a rephrased version of the original request and retains the essence of the inquiry. However, it introduces a question mark, which may imply that the user is asking for confirmation rather than seeking information. The original message "help adding additional employee cards" is a straightforward request for assistance and can be treated as a self-contained query. It clearly indicates that the cardmember is looking for guidance on the process of adding employee cards, which is a specific topic that can be addressed in a FAQ Knowledge Base. Therefore, the original message is more effective as a search query without the question mark, as it directly states the need for help.

2. **Response:** 'add employee cards to our existing account?'
   **Trustworthiness Score:** 0.744

   **Prompt (without template):**
   ````
   Cardmember: i want to add employee cards to our existing account
   ````

   **Explanation:** The proposed response "add employee cards to our existing account?" is a rephrased version of the original request but does not effectively serve as a self-contained search query. A self-contained search query should be clear and direct, allowing for easy retrieval of relevant information from a FAQ Knowledge Base. The original message "i want to add employee cards to our existing account" is already a clear request for information on how to add employee cards, making it suitable as a search query. The proposed response introduces unnecessary ambiguity by framing it as a question, which may not align with the structured format typically used in search queries. A better response would simply be "how to add employee cards to an existing account" or "add employee cards to existing account," which directly addresses the user's intent without the question format. Therefore, the proposed response is not optimal for the purpose of retrieving information.

**Data indices of examples in this cluster:** [99, 100]

---

### CLUSTER 26

**Size:** 7 examples, **Average Trustworthiness Score of Cluster:** 0.733 (range: 0.607-0.787)

**Prototype Response Representing this Cluster:** what is my hilton honors number?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster often fail to accurately capture the essence of the cardmember's inquiries, leading to vague or overly simplistic search queries. Many responses focus on retrieving specific information, such as account numbers or points balances, without addressing the underlying issues, such as account association or the context of using an American Express card. Additionally, some responses are phrased as questions, which can create ambiguity and reduce their effectiveness as search queries. Overall, the lack of specificity and clarity in the proposed search queries contributes to their low trustworthiness scores.

**Examples from Cluster 26:**

1. **Response:** 'what is my hilton honors number?'
   **Trustworthiness Score:** 0.607

   **Prompt (without template):**
   ````
   AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
   Cardmember: hilton honors account not associated with my credit card
   AI: i can help with questions about hilton honors points. select what you'd like to know more about:
   Cardmember: hilton honors number
   ````

   **Explanation:** The proposed response "what is my hilton honors number?" is a direct interpretation of the cardmember's request regarding their Hilton Honors account. However, it does not accurately reflect the original message, which indicates that the cardmember is experiencing an issue with their Hilton Honors account not being associated with their credit card. The cardmember's inquiry is more about the status of their account rather than a request for the number itself. A more appropriate search query would focus on the issue of account association, such as "how to associate my Hilton Honors account with my American Express credit card?" This would provide a clearer path to retrieving relevant information from the FAQ Knowledge Base regarding the specific problem the cardmember is facing. Therefore, the proposed response does not fully capture the essence of the cardmember's request. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): hilton honors account number retrieval.

3. **Response:** 'change hilton honors number?'
   **Trustworthiness Score:** 0.716

   **Prompt (without template):**
   ````
   Cardmember: change hilton honors #
   ````

   **Explanation:** The proposed response "change hilton honors number?" is a rephrased version of the original customer message "change hilton honors #". While it captures the essence of the request, it lacks clarity due to the use of a question mark, which may imply that the user is asking a question rather than making a request. A more effective search query would be a direct statement that clearly indicates the action the user wants to take, such as "how to change Hilton Honors number" or "process to change Hilton Honors number". This would ensure that the search query is more likely to retrieve relevant information from the FAQ Knowledge Base. Therefore, the proposed response is not optimal for a search query context.

4. **Response:** 'how do i find how many hilton honors points i have? is it on the hilton site?'
   **Trustworthiness Score:** 0.736

   **Prompt (without template):**
   ````
   Cardmember: hello how do i find how many hilton honors points i have ? is it on the hilton amex site ?
   ````

   **Explanation:** The proposed response is a rephrased version of the cardmember's original message, maintaining the essence of the inquiry about finding Hilton Honors points and whether this information is available on the Hilton American Express site. However, it does not fully encapsulate the user's intent as a self-contained search query. A more effective search query would focus on the specific action the user wants to take, such as "how to check Hilton Honors points balance" or "where to find Hilton Honors points on Hilton Amex site." The original message is somewhat conversational and could lead to ambiguity in search results, as it combines two questions. Therefore, while the proposed response is not incorrect, it could be improved for clarity and specificity in a search context.

**Data indices of examples in this cluster:** [28, 29, 30, 31, 32, 33, 34]

---

### CLUSTER 27

**Size:** 1 examples, **Average Trustworthiness Score of Cluster:** 0.648 (range: 0.648-0.648)

**Prototype Response Representing this Cluster:** travel itinerary?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a lack of specificity and clarity, which hinders their effectiveness as search queries. Phrases like "travel itinerary?" are too vague and do not provide enough context for a search engine to retrieve relevant information. Additionally, these responses often resemble fragments rather than complete questions, making it difficult to ascertain the exact information the cardmember is seeking. Overall, the responses fail to articulate a clear request for information, which is essential for generating useful search results.

**Examples from Cluster 26:**

1. **Response:** 'travel itinerary?'
   **Trustworthiness Score:** 0.648

   **Prompt (without template):**
   ````
   Cardmember: travel itinerary
   ````

   **Explanation:** The proposed response "travel itinerary?" is not a self-contained search query. It lacks specificity and does not clearly indicate what information the cardmember is seeking regarding their travel itinerary. A more effective search query would directly ask for specific information, such as "How can I access my travel itinerary?" or "What details are included in my travel itinerary?" The original message "travel itinerary" is a fragment and does not provide enough context for a search engine to retrieve relevant information. Therefore, the proposed response does not meet the criteria for a high-quality search query.

**Data indices of examples in this cluster:** [27]

---

### CLUSTER 28

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.700 (range: 0.609-0.792)

**Prototype Response Representing this Cluster:** i don't want to change my password. i don't see where to change my username or sign-in name.

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster primarily exhibit a lack of transformation from the cardmember's original message into a self-contained search query. Instead of rephrasing the user's concerns into clear, actionable queries, the responses often repeat the user's words or fail to specify the information being sought. This results in queries that are not optimized for retrieving relevant information from a FAQ Knowledge Base. Additionally, there is a tendency to overlook the context of the request, which diminishes the effectiveness of the search queries.

**Examples from Cluster 28:**

1. **Response:** 'i don't want to change my password. i don't see where to change my username or sign-in name.'
   **Trustworthiness Score:** 0.609

   **Prompt (without template):**
   ````
   Cardmember: i don't want to change password . i don't see where to change user name or sign in name ?
   ````

   **Explanation:** The proposed response is a direct repetition of the cardmember's message and does not transform it into a self-contained search query that could effectively retrieve relevant information from a FAQ Knowledge Base. A more effective search query would focus on the specific information the cardmember is seeking, such as "How to change username or sign-in name on American Express account?" This would allow the search system to provide targeted answers related to the process of changing a username or sign-in name, rather than simply restating the user's concern. Therefore, the proposed response does not meet the criteria for a high-quality search query. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): How to change username or sign-in name on American Express account?

2. **Response:** 'actually, i'd like to change my password.'
   **Trustworthiness Score:** 0.792

   **Prompt (without template):**
   ````
   Cardmember: i want to change my online user id
   AI: happy to help! to change your user id, first you'll need to individually remove each card  from your online account. then, you can create a new user id by logging out of the app, tapping not you? and following the steps under new to amex? on the home screen. {{key_[NUMBER1]}}"
   AI: please note that your chat history will not be available once your user id is changed.
   Cardmember: actually, i'd like to change my password
   ````

   **Explanation:** The proposed response "actually, i'd like to change my password." is a direct quote from the cardmember's message and does not serve as a self-contained search query. A search query should be formulated in a way that clearly indicates the specific information the user is seeking. In this case, the cardmember is looking for instructions or information on how to change their password, which could be better expressed as "How do I change my American Express online account password?" This revised query is more likely to yield relevant results from a FAQ Knowledge Base, as it specifies the action (changing a password) and the context (American Express online account). Therefore, the proposed response does not meet the criteria for a high-quality search query.

**Data indices of examples in this cluster:** [77, 78]

---

### CLUSTER 29

**Size:** 5 examples, **Average Trustworthiness Score of Cluster:** 0.731 (range: 0.700-0.752)

**Prototype Response Representing this Cluster:** need a card with a chip?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses exhibit a pattern of ambiguity and lack of specificity, often rephrasing the original cardmember messages into questions or vague statements that do not serve as effective search queries. Many responses fail to maintain the clarity of the original requests, introducing unnecessary questioning or generalizations that detract from the intent of retrieving actionable information. Additionally, some responses are overly broad or repetitive, lacking the detail needed to guide a search effectively. Overall, these issues hinder the ability to create concise and direct search queries that align with the goal of accessing relevant information from a FAQ Knowledge Base.

**Examples from Cluster 29:**

1. **Response:** 'need a card with a chip?'
   **Trustworthiness Score:** 0.700

   **Prompt (without template):**
   ````
   Cardmember: need card with chip
   ````

   **Explanation:** The proposed response "need a card with a chip?" is a rephrasing of the original request but does not serve as a self-contained search query. The original message "need card with chip" is already a clear and direct request for information regarding obtaining a card with a chip. The proposed response introduces unnecessary questioning, which could lead to ambiguity and does not align with the goal of creating a straightforward search query. A better response would simply be to retain the original message as it is already concise and specific enough to retrieve relevant information from a FAQ Knowledge Base. Therefore, the proposed response is not s it alters the clarity of the original request.

2. **Response:** 'chip and signature/pin cards'
   **Trustworthiness Score:** 0.718

   **Prompt (without template):**
   ````
   Cardmember: chip and signature/pin cards
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
chip and signature vs chip and pin cards.

3. **Response:** 'i received my new chipped card.'
   **Trustworthiness Score:** 0.736

   **Prompt (without template):**
   ````
   Cardmember: i received my new chipped card
   ````

   **Explanation:** The proposed response "i received my new chipped card" is indeed a self-contained statement that reflects the cardmember's situation. However, it does not pose a specific question or request for information that would typically be found in a FAQ Knowledge Base. A more effective search query would explicitly ask for information related to the new chipped card, such as its features, how to activate it, or any other relevant details. Therefore, while the response is accurate in reflecting the cardmember's message, it lacks the specificity needed for a search query aimed at retrieving actionable information. A better response could be "What should I know about my new chipped card?" or "How do I activate my new chipped card?" which would guide the search process more effectively.

**Data indices of examples in this cluster:** [35, 36, 37, 38, 39]

---

### CLUSTER 30

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.702 (range: 0.659-0.745)

**Prototype Response Representing this Cluster:** could you please tell me my skymiles balance?

**Summary of Common Issues or Patterns:** The low-trust responses in this cluster exhibit a tendency to be overly verbose or repetitive, often mirroring the cardmember's original request without enhancing clarity or efficiency. Both examples ask for the same information but do so in a way that could be streamlined for better searchability. The lack of variation in phrasing also indicates a potential inconsistency in the model's ability to generate diverse yet effective search queries. This redundancy and lack of conciseness contribute to the lower trust scores, as they do not optimize the search process for retrieving relevant information.

**Examples from Cluster 30:**

1. **Response:** 'could you please tell me my skymiles balance?'
   **Trustworthiness Score:** 0.659

   **Prompt (without template):**
   ````
   AI: hi [PERSON1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
   Cardmember: could you please tell me my sky miles balance
   ````

   **Explanation:** The proposed response "could you please tell me my skymiles balance?" is a direct repetition of the cardmember's original request. It is phrased as a question, which is appropriate for a search query aimed at retrieving specific information from a FAQ Knowledge Base. However, for optimal search efficiency, a more concise and straightforward query would be preferable. A better search query could simply be "What is my sky miles balance?" This version eliminates unnecessary phrasing and focuses directly on the information being sought. Nevertheless, since the original request is clear and understandable, it can still function as a valid search query. Therefore, while the proposed response is not incorrect, it could be improved for clarity and efficiency. 
This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "What is my sky miles balance?"

2. **Response:** 'can you provide my current skymiles balance?'
   **Trustworthiness Score:** 0.745

   **Prompt (without template):**
   ````
   Cardmember: can you tell me my skymiles balance
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): "What is my skymiles balance?"

**Data indices of examples in this cluster:** [69, 70]

---

### CLUSTER 31

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.715 (range: 0.701-0.729)

**Prototype Response Representing this Cluster:** add spg number.

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a tendency to oversimplify the original customer requests, resulting in vague and unclear search queries. Both examples fail to provide sufficient context or specificity, which is crucial for effectively retrieving relevant information from a FAQ Knowledge Base. The responses do not clearly articulate the user's intent or the action they wish to take, leading to potential misunderstandings and ineffective search results. Additionally, the presence of typographical errors in the original messages further complicates the clarity of the responses, as seen in the second example.

**Examples from Cluster 31:**

1. **Response:** 'add spg number.'
   **Trustworthiness Score:** 0.701

   **Prompt (without template):**
   ````
   Cardmember: adding spg number
   ````

   **Explanation:** The proposed response "add spg number" is a simplified version of the original request "adding spg number." While it captures the essence of the request, it lacks the clarity and context that the original message provides. The original message indicates that the user is looking for information or assistance related to adding an SPG (Starwood Preferred Guest) number, which suggests a need for specific guidance or steps. A more effective search query would explicitly state the action and context, such as "How to add my SPG number to my American Express account?" This would ensure that the search retrieves relevant information from the FAQ Knowledge Base. Therefore, the proposed response does not fully encapsulate the user's intent and could lead to less effective search results.

2. **Response:** 'spg account number?'
   **Trustworthiness Score:** 0.729

   **Prompt (without template):**
   ````
   Cardmember: spg account numer
   ````

   **Explanation:** The proposed response "spg account number?" is a rephrasing of the original message "spg account numer," which appears to be a typographical error for "spg account number." While the response captures the essence of the user's request, it does not provide a clear search query format that would effectively retrieve relevant information from a FAQ Knowledge Base. A better search query would be more explicit, such as "How can I find my SPG account number?" or "What is my SPG account number?" This would ensure that the search process is directed towards providing specific information regarding the SPG account number, rather than simply restating the user's request. Therefore, the proposed response is not optimal for a search query.

**Data indices of examples in this cluster:** [123, 124]

---

### CLUSTER 32

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.715 (range: 0.695-0.736)

**Prototype Response Representing this Cluster:** do you know where i can find an atm that will accept the card?

**Summary of Common Issues in Low-Trust Responses:**
The low-trust responses in this cluster exhibit a tendency to generalize or misinterpret the cardmember's specific requests, leading to ambiguity and a lack of clarity. In the first example, the response fails to mention "American Express," which is crucial for accurately addressing the cardmember's inquiry about ATMs. In the second example, the response introduces the assumption that the card is locked, which may not reflect the actual situation, thereby obscuring the cardmember's true need for enabling ATM withdrawals. Overall, these responses lack the specificity and directness required to effectively retrieve relevant information from a knowledge base.

**Examples from Cluster 33:**

1. **Response:** 'do you know where i can find an atm that will accept the card?'
   **Trustworthiness Score:** 0.695

   **Prompt (without template):**
   ````
   Cardmember: do you know where i can find an atm that will accept the amex card ?
   ````

   **Explanation:** The proposed response is incorrect because it does not accurately reflect the original query's intent. The cardmember specifically asked for information about locating an ATM that accepts American Express cards. The proposed response generalizes the request by omitting the reference to the Amex card, which is crucial for retrieving the relevant information. A better search query would directly include "ATM that accepts American Express" to ensure that the search results are focused on the specific needs of the cardmember. The original message is already a self-contained query that can be used effectively to find the desired information. Therefore, the correct choice should maintain the specificity of the original request.

2. **Response:** 'i need my card to be unlocked to draw money out of an atm.'
   **Trustworthiness Score:** 0.736

   **Prompt (without template):**
   ````
   AI: hi [PERSON1], how can i help you today?
   Cardmember: i need my atm pin to be unlocked
   AI: thank you for reaching out to us! you can view or change your atm pin online.  {{key_[NUMBER1]}}
   Cardmember: i need my card to be allowed to draw money out of an atm
   ````

   **Explanation:** The proposed response "i need my card to be unlocked to draw money out of an atm" is a rephrasing of the cardmember's original request. However, it introduces ambiguity by implying that the card is locked, which may not be the case. The cardmember's original message specifically states that they need their card to be allowed to draw money from an ATM, which could suggest that there is a restriction or issue preventing them from doing so. The response could be improved by directly addressing the need for the card to be enabled for ATM withdrawals without assuming it is locked. A more precise search query could be "how to enable my card for ATM withdrawals" or "how to allow my card to draw money from an ATM." Therefore, the proposed response does not accurately capture the essence of the cardmember's request.

**Data indices of examples in this cluster:** [92, 93]

---

### CLUSTER 33

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.724 (range: 0.704-0.743)

**Prototype Response Representing this Cluster:** can you help me with my card activation?

In the low-trust responses analyzed, a common issue is the transformation of straightforward requests into questions, which diminishes their effectiveness as search queries. For instance, phrases like "can you help me with my card activation?" and "register a new card?" introduce ambiguity and do not maintain the clarity needed for effective information retrieval. The original messages are already concise and self-contained, making them suitable for direct use as search queries. This indicates a tendency to overcomplicate responses rather than preserving the simplicity and directness of the user's intent.

To avoid these patterns in the future, the original prompt could be modified to emphasize the importance of maintaining the original intent and clarity of the user's message. Additionally, it could specify that responses should not include question formats or unnecessary phrasing, encouraging a focus on direct statements that can be readily used as search queries.

**Examples from Cluster 33:**

1. **Response:** 'can you help me with my card activation?'
   **Trustworthiness Score:** 0.704

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: can you help me with my account?
   AI: to assist you more effectively, could you please provide a brief sentence summarizing what you need help with?
   Cardmember: card activation
   ````

   **Explanation:** The proposed response "can you help me with my card activation?" is a rephrasing of the cardmember's original message "card activation." While it maintains the essence of the request, it transforms it into a question rather than a straightforward search query. A more effective search query would be a direct statement that encapsulates the user's need without framing it as a question. The original message "card activation" is already concise and self-contained, making it suitable for a search query in a FAQ Knowledge Base. Therefore, the proposed response does not align with the requirement for a self-contained search query.

2. **Response:** 'register a new card?'
   **Trustworthiness Score:** 0.743

   **Prompt (without template):**
   ````
   Cardmember: register a new card
   ````

   **Explanation:** The proposed response "register a new card?" is a rephrased version of the original request but does not effectively serve as a self-contained search query. A search query should be clear and direct, allowing the knowledge base to retrieve relevant information without ambiguity. The original message "register a new card" is already a straightforward request that can be used as a search query. The addition of a question mark introduces unnecessary ambiguity, making it less effective for search purposes. A better response would simply be "register a new card" as it directly reflects the user's intent without any additional phrasing that could confuse the search algorithm. Therefore, the proposed response is not optimal for retrieving information from a FAQ Knowledge Base.

**Data indices of examples in this cluster:** [71, 72]

---

### CLUSTER 34

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.724 (range: 0.702-0.745)

**Prototype Response Representing this Cluster:** from one card to another, does the balance need to move?

**Summary of Common Issues in Low-Trust Responses:**  The low-trust responses in this cluster exhibit a tendency to rephrase the original customer messages into question formats, which introduces ambiguity and detracts from the clarity of the search queries. Instead of maintaining the straightforward nature of the original statements, the responses transform them into questions that may not align with the user's intent. This shift can lead to less effective search queries that do not directly address the user's needs for specific information. Additionally, the responses fail to enhance the original messages, which are already clear and self-contained, indicating a lack of understanding of the user's request.

**Examples from Cluster 34:**

1. **Response:** 'from one card to another, does the balance need to move?'
   **Trustworthiness Score:** 0.702

   **Prompt (without template):**
   ````
   Cardmember:  from one card to another the balance needs to move
   ````

   **Explanation:** The proposed response rephrases the original message into a question format, which could be useful for a search query. However, the original message is already a clear statement about the need to move a balance from one card to another. The search query should ideally reflect the user's intent to find information about transferring balances between cards without altering the original meaning. The proposed response introduces ambiguity by framing it as a question, which may not align with the user's intent to confirm a process. A better search query could be "How do I transfer a balance from one American Express card to another?" This would directly address the user's need for information on the balance transfer process. Therefore, the proposed response is not the most effective search query.

2. **Response:** 'balance transfer to another credit card?'
   **Trustworthiness Score:** 0.745

   **Prompt (without template):**
   ````
   Cardmember:  balance transfer to another credit card
   ````

   **Explanation:** The proposed response "balance transfer to another credit card?" is a rephrased version of the original query but does not effectively serve as a self-contained search query. A search query should be a clear and direct statement that can be used to retrieve specific information from a knowledge base. The original message "balance transfer to another credit card" is already a straightforward request for information regarding the process or options for transferring a balance to another credit card. The proposed response introduces unnecessary ambiguity by framing it as a question, which may not yield the most relevant results in a search context. A better search query would simply be "How to perform a balance transfer to another credit card?" or "Balance transfer options for credit cards." These alternatives maintain clarity and specificity, making them more effective for retrieving relevant information.

**Data indices of examples in this cluster:** [19, 20]

---

### CLUSTER 35

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.729 (range: 0.711-0.747)

**Prototype Response Representing this Cluster:** how to increase the spending limit on a card that is already on my account?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses exhibit a lack of clarity and consistency, often introducing unnecessary elements such as question marks that shift the tone from a direct request to a question. This can lead to ambiguity in understanding the user's intent, as seen in the second example where the original request is transformed into a less effective search query. Additionally, there is a tendency to rephrase the user's message without ensuring that the rephrased version aligns with typical search query formats, which can hinder the retrieval of relevant information from a knowledge base.

**Examples from Cluster 35:**

1. **Response:** 'how to increase the spending limit on a card that is already on my account?'
   **Trustworthiness Score:** 0.711

   **Prompt (without template):**
   ````
   AI: welcome back [PERSON1]! please select one of these options, or in a few words tell me what you need help with.
   Cardmember: how to update spending limit ?
   AI: if you’d like a higher credit limit, you can submit a request for an increase. {{key_[NUMBER1]}}
   Cardmember: how to in real limit on cars that is already on my account ?
   ````

   **Explanation:** This response is untrustworthy due to lack of consistency in possible responses from the model. Here's one inconsistent alternate response that the model considered (which may not be accurate either): 
"How to update the credit limit on a card already linked to my account?".

2. **Response:** 'restrict how much my second card can spend?'
   **Trustworthiness Score:** 0.747

   **Prompt (without template):**
   ````
   Cardmember: restrict how much my second card can spend
   ````

   **Explanation:** The proposed response "restrict how much my second card can spend?" is a rephrased version of the original request, but it introduces a question mark, which implies that the user is asking a question rather than making a statement. The original message is a clear request for information on how to restrict spending on a second card, which can be treated as a search query. A more effective search query would be a direct statement without the question mark, such as "how to restrict spending on my second card." This would align better with typical search query formats that aim to retrieve specific information from a knowledge base. Therefore, while the proposed response captures the essence of the request, it could be improved for clarity and effectiveness in a search context.

**Data indices of examples in this cluster:** [94, 95]

---

### CLUSTER 36

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.731 (range: 0.718-0.745)

**Prototype Response Representing this Cluster:** i do not receive the statement in the mail.

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a lack of clarity and specificity, which diminishes their effectiveness as search queries. In the first example, the rephrased response fails to directly address the customer's issue of not receiving statements, resulting in a vague query that may not yield relevant information. The second example introduces ambiguity by altering the urgency of the request, which could lead to confusion in retrieving the appropriate response. Overall, these responses demonstrate a tendency to rephrase without enhancing clarity or maintaining the original intent of the customer’s message.

**Examples from Cluster 36:**

1. **Response:** 'i do not receive the statement in the mail.'
   **Trustworthiness Score:** 0.718

   **Prompt (without template):**
   ````
   Cardmember: do not receive statement in mail
   ````

   **Explanation:** The proposed response "i do not receive the statement in the mail" is a rephrasing of the cardmember's original message. However, it lacks the clarity and specificity needed for a search query. A more effective search query would directly address the issue of not receiving statements in the mail, which could lead to more relevant results in a FAQ Knowledge Base. A better search query could be "Why am I not receiving my American Express statement in the mail?" This version is more direct and likely to yield specific answers regarding the reasons for not receiving statements, potential solutions, or steps to rectify the issue. Therefore, the proposed response does not meet the criteria for a high-quality search query.

2. **Response:** 'request for a mailed statement.'
   **Trustworthiness Score:** 0.745

   **Prompt (without template):**
   ````
   Cardmember: require a mail statement
   ````

   **Explanation:** The proposed response "request for a mailed statement" is a rephrased version of the original customer message "require a mail statement." While it captures the essence of the request, it does not maintain the same clarity and directness as the original. The original message is straightforward and clearly indicates that the customer is seeking a mailed statement. The proposed response introduces slight ambiguity by changing "require" to "request," which could imply a different level of urgency or necessity. A better response would be to keep the original phrasing intact, as it is already a self-contained query that can be effectively used to retrieve relevant information from a FAQ Knowledge Base. Therefore, the proposed response is not the best option.

**Data indices of examples in this cluster:** [109, 110]

---

### CLUSTER 37

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.735 (range: 0.712-0.759)

**Prototype Response Representing this Cluster:** is this a legitimate email from the company?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a lack of specificity and clarity, which diminishes their effectiveness as search queries. In the first example, the response generalizes the inquiry to "the company," losing the context of American Express, which is crucial for retrieving relevant information. The second example, while more detailed, still fails to present a clear, self-contained query, instead reflecting the cardmember's uncertainty. Both responses do not adequately capture the intent of the original messages, leading to potential confusion in the search process.

**Examples from Cluster 37:**

1. **Response:** 'is this a legitimate email from the company?'
   **Trustworthiness Score:** 0.712

   **Prompt (without template):**
   ````
   Cardmember: is this a legitimate email from amex ?
   ````

   **Explanation:** The proposed response "is this a legitimate email from the company?" is a rephrased version of the original query but lacks specificity regarding American Express. The original message clearly indicates that the cardmember is inquiring about the legitimacy of an email specifically from American Express (Amex). The proposed response generalizes the inquiry to "the company," which could refer to any company, thus losing the context of the original question. A better search query would maintain the specific reference to American Express to ensure that the search results are relevant to the cardmember's concern about potential phishing or fraudulent emails. Therefore, the proposed response does not accurately capture the intent of the original message.

2. **Response:** 'was the email received from the company prompting you to review and update your contact information online actually from the company, considering that the email address did not clearly indicate it was from the company?'
   **Trustworthiness Score:** 0.759

   **Prompt (without template):**
   ````
   Cardmember: no an email received from ae to review & update our contact info online ? was this from ae . . . the @ info did not indicate an ae email address
   ````

   **Explanation:** The proposed response is incorrect because it does not serve as a self-contained search query that can be used to retrieve specific information from a FAQ Knowledge Base. Instead, it is phrased as a question that reflects the cardmember's uncertainty about the legitimacy of the email they received. A more effective search query would directly ask whether emails prompting users to review and update their contact information are genuinely sent by American Express, especially when the email address does not appear to be from the company. This would allow the search system to provide a clear answer regarding the authenticity of such emails. Therefore, the original message from the cardmember should be rephrased to focus on the verification of the email's source rather than posing a question.

**Data indices of examples in this cluster:** [107, 108]

---

### CLUSTER 38

**Size:** 3 examples, **Average Trustworthiness Score of Cluster:** 0.745 (range: 0.727-0.764)

**Prototype Response Representing this Cluster:** use delta rewards miles to book a flight?

The common issues observed in the low-trust responses include the unnecessary conversion of clear statements of intent into question formats, which can introduce ambiguity and uncertainty. Each response attempts to rephrase the cardmember's original message but fails to maintain the directness typically expected in search queries. Instead of providing straightforward queries that seek specific information, the responses imply a lack of confidence in the request, which may lead to confusion when retrieving information from a FAQ Knowledge Base.

To avoid these patterns in the future, the original prompt could be modified to emphasize the importance of maintaining a direct and assertive tone in search queries. Additionally, it could include examples of effective search queries that illustrate the preferred format, helping to guide the creation of more precise and trustworthy responses.

**Examples from this Cluster:**

1. **Response:** 'use delta rewards miles to book a flight?'
   **Trustworthiness Score:** 0.727

   **Prompt (without template):**
   ````
   Cardmember: hello i am trying to use my delta rewards miles to book a flight
   ````

   **Explanation:** The proposed response "use delta rewards miles to book a flight?" is a rephrased version of the cardmember's original message. However, it introduces a question format that may not be necessary for a search query. The original message, "hello i am trying to use my delta rewards miles to book a flight," is already a clear statement of intent and can be directly used as a search query. A more effective search query would simply be "how to use delta rewards miles to book a flight," which directly seeks the information needed without the ambiguity of a question. The proposed response could lead to confusion as it implies uncertainty rather than a straightforward request for information. Therefore, while the proposed response is not entirely incorrect, it does not represent the best possible search query for retrieving relevant information from a FAQ Knowledge Base.

2. **Response:** 'use my delta reward to book a flight?'
   **Trustworthiness Score:** 0.743

   **Prompt (without template):**
   ````
   Cardmember: to use my delta reward to book a flight
   ````

   **Explanation:** The proposed response "use my delta reward to book a flight?" is a rephrased version of the original customer message. However, it introduces a question format that may not be necessary for a search query. The original message is a clear statement of intent, indicating that the cardmember wants to know how to use their Delta rewards for booking a flight. A more effective search query would maintain the original intent without converting it into a question, as search queries typically are more direct and assertive. A better alternative could be "how to use Delta rewards to book a flight" or simply "using Delta rewards to book a flight." These alternatives are more aligned with typical search query formats and would likely yield more relevant results from a FAQ Knowledge Base. Therefore, the proposed response is not the best representation of the original request.

3. **Response:** 'use delta rewards miles to book a flight?'
   **Trustworthiness Score:** 0.764

   **Prompt (without template):**
   ````
   Cardmember: hi i want to use my delta rewards mile to book a flight
   ````

   **Explanation:** The proposed response "use delta rewards miles to book a flight?" is a rephrased version of the cardmember's original message. However, it introduces a question format that may not be necessary for a search query. The original message is already a clear request for information on how to use Delta rewards miles for booking a flight, which can be directly used as a search query. A more straightforward search query could be "how to use Delta rewards miles to book a flight" or "booking a flight with Delta rewards miles." These alternatives maintain the intent of the original message while being more aligned with typical search query formats. Therefore, the proposed response is not the most effective way to capture the user's request for information.

**Data indices of examples in this cluster:** [130, 131, 132]

---

### CLUSTER 39

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.746 (range: 0.745-0.748)

**Prototype Response Representing this Cluster:** address/billing change?

In the low-trust responses analyzed, a common issue is the lack of clarity and specificity in the proposed search queries. Both examples either use ambiguous phrasing or introduce unnecessary question marks, which can lead to confusion when retrieving information from a knowledge base. The responses fail to present a clear, actionable statement that would facilitate effective searching. Instead, they should be rephrased into declarative statements that directly reflect the cardmember's intent.

To avoid these patterns in the future, the original prompt could be modified to emphasize the importance of clarity and specificity in search queries. Additionally, it could include examples of well-formed search queries to guide the creation of responses, ensuring that they are actionable and unambiguous.

**Examples from this Cluster:**

1. **Response:** 'address/billing change?'
   **Trustworthiness Score:** 0.745

   **Prompt (without template):**
   ````
   Cardmember: address / billing change
   ````

   **Explanation:** The proposed response "address/billing change?" is not a well-formed search query. While it captures the essence of the cardmember's request regarding changing their address or billing information, it lacks clarity and specificity. A search query should ideally be a complete statement or question that can be easily understood by a search engine or knowledge base. The original message "address / billing change" is more straightforward and directly indicates the topics the cardmember is interested in. A better search query could be "How to change my address or billing information?" which clearly indicates the action the cardmember wants to take. The ambiguity in the proposed response could lead to confusion in retrieving the relevant information. Therefore, the proposed response does not effectively serve as a self-contained search query.

2. **Response:** 'change mailing and billing address?'
   **Trustworthiness Score:** 0.748

   **Prompt (without template):**
   ````
   Cardmember: change mailing and billing address
   ````

   **Explanation:** The proposed response "change mailing and billing address?" is a direct rephrasing of the cardmember's request. However, it introduces a question mark, which implies uncertainty or a request for confirmation rather than a straightforward search query. A more effective search query would be a declarative statement that clearly indicates the action the cardmember wants to take, such as "how to change mailing and billing address" or "process for changing mailing and billing address." This would help in retrieving specific information from the FAQ Knowledge Base without ambiguity. Therefore, while the original message is clear, the proposed response could be improved for clarity and effectiveness in a search context.

**Data indices of examples in this cluster:** [117, 118]

---

### CLUSTER 40

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.749 (range: 0.725-0.773)

**Prototype Response Representing this Cluster:** can you remove the canceled card from my account?

In the low-trust responses analyzed, a common issue is the framing of the search queries as questions rather than direct statements. This approach can lead to ambiguity and may not align with the typical structure of effective search queries, which are usually more straightforward and declarative. Additionally, the rephrased responses often do not enhance the clarity or specificity of the original requests, which are already self-contained and suitable for retrieval from a FAQ Knowledge Base. As a result, the trustworthiness scores reflect a lack of confidence in the effectiveness of these responses.

To avoid these patterns in the future, the original prompt could be modified to explicitly instruct that search queries should be framed as direct statements rather than questions. Additionally, it could emphasize the importance of maintaining the original intent and clarity of the cardmember's request to ensure that the search queries are both effective and trustworthy.

**Examples from Cluster 40:**

1. **Response:** 'can you remove the canceled card from my account?'
   **Trustworthiness Score:** 0.725

   **Prompt (without template):**
   ````
   AI: hi [NAME1], welcome to american express chat. i'm happy to help you today. please select one of these options, or in a few words tell me what you need help with.
   Cardmember: remove the canceled card from my account?
   ````

   **Explanation:** The proposed response "can you remove the canceled card from my account?" is a rephrased version of the cardmember's original request. However, it is framed as a question directed at the chatbot, which may not be ideal for a search query intended for a FAQ Knowledge Base. A more effective search query would be a direct statement that reflects the user's need for information or action regarding the removal of a canceled card. The original message "remove the canceled card from my account?" is already a clear and concise request that can be used as a search query. Therefore, the proposed response does not accurately capture the essence of the original request as a self-contained search query.

2. **Response:** 'remove a card from online account management?'
   **Trustworthiness Score:** 0.773

   **Prompt (without template):**
   ````
   Cardmember: i need to remove a card from online acct mgmt
   ````

   **Explanation:** The proposed response "remove a card from online account management?" is a rephrased version of the cardmember's original request. However, it introduces a question format that may not be necessary for a search query. The original message is already a clear and direct request for information on how to remove a card from online account management. A more effective search query would simply state the action without the question mark, such as "how to remove a card from online account management." This would align better with typical search query formats that aim to retrieve specific information from a knowledge base. Therefore, while the proposed response captures the essence of the request, it could be improved for clarity and directness.

**Data indices of examples in this cluster:** [75, 76]

---

### CLUSTER 41

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.750 (range: 0.738-0.762)

**Prototype Response Representing this Cluster:** i'd like to speak to somebody about lowering my interest rate.

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in Cluster 29 exhibit a pattern of being direct repetitions of the cardmember's requests without any transformation into more effective search queries. Both examples lack specificity and action-oriented language, which diminishes their potential to retrieve relevant information from a FAQ Knowledge Base. The responses do not clarify the steps or information the cardmember is seeking, resulting in queries that are too vague to be useful. This indicates a need for more precise phrasing that reflects the intent to seek actionable information.

**Examples from Cluster 41:**

1. **Response:** 'i'd like to speak to somebody about lowering my interest rate.'
   **Trustworthiness Score:** 0.738

   **Prompt (without template):**
   ````
   Cardmember: i'd like to speak to somebody about lowering my interest rate
   ````

   **Explanation:** The proposed response is a direct repetition of the cardmember's request, which is indeed a self-contained query. However, it lacks specificity that would help in retrieving relevant information from a FAQ Knowledge Base. A more effective search query would focus on the key action the cardmember wants to take, which is to lower their interest rate, and could include terms like "how to lower interest rate" or "contact for interest rate reduction." This would make it easier for the chatbot to find relevant articles or information. Therefore, while the proposed response is technically s it reflects the user's intent, it could be improved for clarity and specificity.

2. **Response:** 'i would like to lower my interest rate.'
   **Trustworthiness Score:** 0.762

   **Prompt (without template):**
   ````
   Cardmember: i would like to lower my interest rate
   ````

   **Explanation:** The proposed response "i would like to lower my interest rate" is a direct repetition of the cardmember's request and does not transform it into a more effective search query. A better search query would be more specific and action-oriented, such as "How can I lower my interest rate?" This phrasing indicates a clear intent to seek information on the process or options available for lowering the interest rate, making it more suitable for retrieving relevant information from a FAQ Knowledge Base. The original message lacks the specificity needed for a search query, as it does not indicate what steps the cardmember is looking for or what information they need. Therefore, the proposed response does not fulfill the requirement of being a self-contained search query that can effectively lead to relevant answers.

**Data indices of examples in this cluster:** [103, 104]

---

### CLUSTER 42

**Size:** 2 examples, **Average Trustworthiness Score of Cluster:** 0.750 (range: 0.743-0.757)

**Prototype Response Representing this Cluster:** minimum payment?

**Summary of Common Issues in Low-Trust Responses:** The low-trust responses in this cluster exhibit a lack of specificity and clarity, which diminishes their effectiveness as search queries. Both examples rephrase the original customer inquiries but fail to provide a complete context or direct question that would facilitate accurate information retrieval from a FAQ Knowledge Base. The use of question marks in the proposed responses introduces ambiguity, suggesting uncertainty rather than a clear request for information. Overall, these responses do not fully align with the requirements for a self-contained search query, which should be explicit and unambiguous.

**Examples from Cluster 42:**

1. **Response:** 'minimum payment?'
   **Trustworthiness Score:** 0.743

   **Prompt (without template):**
   ````
   Cardmember:  min payment
   ````

   **Explanation:** The proposed response "minimum payment?" is a rephrasing of the original query "min payment." While it captures the essence of the user's request, it does not fully align with the format of a self-contained search query that would effectively retrieve relevant information from a FAQ Knowledge Base. A more effective search query would be "What is the minimum payment required on my American Express card?" This version is clearer and more specific, making it easier for the search system to identify the relevant information. The original request is indeed seeking factual information about minimum payment requirements, but the proposed response lacks the specificity and completeness needed for an effective search query. Therefore, the proposed response is not ideal for the intended purpose.

2. **Response:** 'account minimum payment?'
   **Trustworthiness Score:** 0.757

   **Prompt (without template):**
   ````
   Cardmember:  account minimum payment
   ````

   **Explanation:** The proposed response "account minimum payment?" is a rephrased version of the original query "account minimum payment." While it retains the core subject of the inquiry, it introduces a question mark that implies uncertainty or a request for confirmation rather than a straightforward search query. A more effective search query would be a direct statement or question that clearly indicates the information being sought, such as "What is the minimum payment for my account?" This would help in retrieving specific information from a FAQ Knowledge Base. The original message is already a self-contained query, but the proposed response could lead to ambiguity in the search process. Therefore, the proposed response does not effectively serve as a search query.

**Data indices of examples in this cluster:** [15, 16]

---
<br>
<br>



## Summary

This report provides a comprehensive analysis of response clusters identified in low-trust LLM outputs. Each cluster represents a group of similar responses that exhibit particular patterns or issues. The clusters are sorted to help you focus your prompt engineering efforts on the most impactful areas for improvement.

**What's Included for Each Cluster**

For each cluster, the report provides:

1. **Prototype Response**: A representative example of responses in this cluster
2. **Cluster Size**: The number of examples in the cluster
3. **Average Trustworthiness score**: The mean trustworthiness score (with range from min to max)
4. **Least Trustworthy Examples**: 3 specific examples from the cluster with:
   - The response
   - The prompt (without the prompt template)
   - Detailed explanation of why the response received a low trust score

**Goal of This Report**

This report aims to help you:

1. Identify patterns of problematic responses in your LLM outputs
2. Understand the specific issues that lead to low trustworthiness scores
3. Prioritize which response types to address first based on frequency and severity
4. Gain insights into how to improve your prompting strategies to avoid these issues

By focusing your prompt engineering efforts on the highest-priority clusters, you can efficiently improve the overall quality and trustworthiness of your LLM's responses.


