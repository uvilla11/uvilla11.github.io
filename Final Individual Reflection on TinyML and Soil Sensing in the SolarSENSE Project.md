# 

# 

# 

# 

# 

# 

# 

# 

# 

# 

# 

# 

# 

# **Final Individual Reflection on TinyML and Soil Sensing in the SolarSENSE Project**

## Uriah D. Villa

## Arizona State University

## EGR 598: Engineering in Global Development

## Dr. Laura Hosman and Professor Bruce Baikie

## May 6, 2025

# 

# **I. Introduction**

The SolarSPELL initiative presents a unique opportunity to engage with technology for impactful global solutions. Participating in the SolarSPELL course offered a hands-on experience in applying technology to real-world challenges. Our project within this course focused on developing an innovative smart agriculture system that utilized Tiny Machine Learning (TinyML) in conjunction with an ESP32-based soil sensor, the LILYGO T-Higrow. The primary aim was to leverage TinyML with sensor readings from the LILYGO T-Higrow to predict soil quality levels. A crucial aspect of our work involved adapting our predictive model to use the board's available onboard salinity (EC) and moisture sensors, providing users with actionable recommendations for improving soil health based on these specific inputs.  
Within this project, my central role involved a significant technical integration: merging the machine learning model code provided by, developed, and deployed using Edge Impulse with the LILYGO T-Higrow's existing firmware. This firmware already utilizes the ESP DASH framework to display sensor data to a web address that can be accessed by devices connected to the LILYGO T-Higrow via wifi. My task was to ensure that our TinyML model's predictions and relevant sensor data were presented on the web-based dashboard hosted directly by the ESP32 microcontroller. This paper will critically examine my contributions to this project, the functioning and dynamics of our team, and my overall learning experience within the SolarSPELL course. This reflection will explore what aspects went well, identify areas for potential course improvement, and reflect on how I might have approached the semester differently, ultimately evaluating how the course and my actions affected the final product.

# **II. My Contributions**

My contributions to the SolarSPELL project were twofold, involving technical work on the project itself and the supportive actions I took to further the team's overall progress on this project.

## ***A. My Contribution to the Project***

My contributions began with the foundational steps of our TinyML model. I worked with my teammate, Ragde, to create and label the data for our initial Edge Impulse model. This combined effort was instrumental in developing an ML model, which, through iterative refinement, eventually exceeded 94% accuracy. A significant challenge we encountered early on was adapting our model. The initial dataset the professors provided us included NPK (Nitrogen, Phosphorus, Potassium) values of the soil, and the professors provided the ideal values based on that data. However, our LILYGO T-Higrow board was not equipped with these sensors; instead, it had light, temperature, humidity, salinity (EC), and moisture sensors. Recognizing this discrepancy, a substantial part of our team's effort, and my focus, shifted to retraining and validating a new model based on the sensor data we could practically and reliably collect from our hardware, which involved the salinity and moisture sensors.  
Once this refined model had achieved over 94% accuracy using the EC and moisture data, it was developed and deployed from the Edge Impulse platform to work with the Arduino IDE. At this point, my primary technical responsibility came to the forefront—merging the deployed model code with the existing firmware on the LILYGO T-Higrow board. The board’s firmware was already configured to display essential sensor readings via the ESP DASH dashboard framework. I aimed to incorporate our TinyML model's predictive capabilities into this existing structure to allow us to connect to the board and display the results on the webpage.  
This integration process presented many technical hindrances. A significant challenge in the beginning was simply understanding the different file types, including various configuration and header files that were made with the Edge Impulse model. To navigate these files efficiently, I used Google Gemini by feeding the files of code to the AI so I could get clear descriptions and explanations for each component, significantly accelerating my comprehension of the code I needed to work with and integrate.  
The subsequent task of combining the ESP DASH code with the Edge Impulse model code was an iterative and demanding process. Again, I leveraged Google Gemini extensively as a development and debugging partner. I would attempt to compile the combined code within the Arduino IDE, and once I encountered some errors, I would feed these error messages to Gemini so that it could understand what was going wrong and provide feedback on what I could do next. The analysis of the error logs by Gemini often gave me insights and direct suggestions that helped pinpoint and fix the underlying issues within the code. This process of debugging greatly increased my productivity and helped create the functional Arduino project. The successful outcome of this intensive effort was a working system where the ESP32 could read sensor data, process it locally through the integrated TinyML model, and then display the soil health predictions along with the raw sensor data on the ESP DASH dashboard, all hosted on the LILYGO T-Higrow itself.

## ***B. My Contribution to the Team***

Beyond my direct technical work, I contributed to the team's work, effectiveness, and collaborative environment. When identifying the need for focused, out-of-class work sessions, I offered my apartment as a meeting place for which I provided a dedicated space where we could meet, focus, and collaborate without the distractions of a public or campus setting, allowing for more productive work sessions.  
Furthermore, I contributed heavily to our team discussions on how to approach the project. These discussions were particularly important in the early stages of the project modules or when interpreting new class assignments. I would help in clarifying objectives for our in-class demonstrations and made sure we understood our weekly goals. This collaborative sense-making was vital for keeping our team focused and moving forward together.

# **III. Personal Course Experience**

The SolarSPELL course was a dynamic and engaging learning environment, offering a combination of successes, learning opportunities, and reflections on potential improvements.

## ***A. What went well for me in this course?***

A significant success from my perspective was our team's ability to develop and significantly refine our TinyML model. Achieving an initial accuracy of around 82% was a good start, but iteratively improving this to over 94% through better data and model adjustments was a substantial mark of progress in this course. Even more satisfying was our successful pivot when faced with hardware limitations; adapting our model from the initial NPK dataset to utilize the board's salinity (EC) and moisture sensors demonstrated our practical problem-solving and adaptability skills. These successes ensured our project remained feasible and relevant to the hardware we were using.  
The core technical task of integrating the Edge Impulse code with the ESP32 firmware and the ESP DASH framework was a challenging yet worthwhile effort. Working through the different software components using Google Gemini to comprehend the unfamiliar code structures and for real-time debugging assistance felt like a significant personal accomplishment. Having the combined code successfully flash onto the LILYGO T-Higrow and verifying that it performed as intended, making predictions based on live sensor readings, gave me a deep feeling of satisfaction and validated the intensive effort I put into the project. The hands-on nature of this troubleshooting and code integration process was incredibly engaging and solidified my understanding of embedded ML systems on edge devices.

## ***B. What could be improved in this course?***

While the course was valuable and part of a noble effort to apply technology for good, one area for potential improvement lies in the dynamic promoted between the two student teams. In the class, the students were split into two teams working towards the final project goal. While this naturally created a degree of healthy competition, an unintended consequence was the emergence of a noticeable rivalry.  
Although our interactions were never openly malicious or hostile, this rivalry contributed to some information siloing. There were instances where insights or technical solutions discovered by one team were intentionally, or maybe unintentionally, withheld from the other. Our team acted similarly, becoming more guarded with our findings and our techniques. This atmosphere ultimately restricted potential cross-team learning and sharing problem-solving strategies. Our team was hesitant to approach the other team for assistance or even to ask for their opinions on our challenges. I suspect that the other team may have experienced a similar hesitation in asking for or providing help. To address this problem, the course structure should explicitly encourage inter-team consultation and knowledge sharing. There should be sessions for teams to share progress, discuss common roadblocks, and offer mutual advice that could be beneficial for the entire class. Promoting a more collaborative work environment between the teams while preserving the motivational aspects of distinct project ownership could significantly improve the learning experience and lead to even more advanced project outcomes for all students involved.

## ***C. What would I do differently if I had the semester to do over again?***

Reflecting on the semester, particularly the inter-team dynamic, I would make a more conscious effort to bridge the communication gap with the other team. I could have suggested informal joint problem-solving sessions when both teams grappled with similar technical hurdles.  
Regarding my technical process, while the use of Google Gemini proved to be an incredibly effective tool for understanding and debugging, I might also dedicate more upfront time to gain a more profound, foundational knowledge of the core libraries involved, such as ESP DASH, before diving headfirst into the integration. While the AI assistance was invaluable for rapid iteration, a deeper initial grasp of the frameworks could have streamlined the debugging process further. Additionally, I might have pushed myself to explore and experiment with a broader array of features within Edge Impulse to tweak and adjust our model, or different techniques and ways of displaying info for the dashboard, had time and project focus allowed.

# **IV. Team Functioning**

Our team navigated the complexities of this project through a combination of somewhat-defined roles, adaptive leadership, and consistent communication.

## ***A. Structure***

The assignment of roles within our team was primarily an organic process. Team members tended to gravitate towards tasks and responsibilities that aligned with their self-assessed strengths and declared capabilities. This self-imposition of roles generally worked well, allowing all team members to contribute in areas where they felt most confident and competent.  
Regarding leadership, there wasn't a single formally designated team leader for the course duration. Instead, leadership tended to be situational and shared. In our team’s case, my teammate Ragde, who seemed to be interested in the Edge Impulse platform and data handling, naturally took the responsibility during the phases involving data sampling, model training, and understanding the dataset from Rwanda. He guided our efforts in these areas and was the go-to person for Edge Impulse-related questions. Conversely, when the project's focus shifted towards the software aspects, specifically about integrating the trained model with the ESP32's firmware and getting the code to run effectively, I found myself taking on more of a leading role in designing and troubleshooting the combined Arduino code for deployment onto the LILYGO T-Higrow board.

## ***B. Dynamics***

Communication was a key factor for our team's functionality. Our primary way of communication was through a dedicated Discord server, which allowed us to have quick exchanges, file sharing, and share weekly updates on progress and meeting dates. We also the held regular physical meetings once or twice weekly at my apartment, typically scheduled before our class session on Wednesdays. Having these face-to-face meetings were helpful for having an in-depth discussion, solidifying plans, and ensuring everyone was on the same page regarding our goals for the week and the project.  
During these meetings, we would lay out the goals we aimed to achieve for the upcoming week or a specific in-class demonstration. We fostered an open and collaborative environment where team members felt comfortable throwing out ideas, brainstorming potential solutions, and discussing the merits of different approaches to meet our objectives. Our team dynamic was very positive, as we were a closely-knit group.

## ***C. Processes***

Our project workflow flowed logically from data acquisition and model development to hardware integration and system testing. This involved initial data exploration and preprocessing, the iterative process of training and refining our TinyML model in Edge Impulse (including the critical adaptation to our available sensors), individual development of specific components (such as my work on the dashboard integration), followed by crucial phases of integrating these components into a cohesive system. Testing was typically done at the component level first, followed by integrated system testing as we brought together different project parts.

## ***D. Challenges***

One of the notable strengths of our team was its internal cohesion. As mentioned, we were a closely communicated group, and this strong connection meant that if any member faced any technical challenges or had questions about a proposed idea, they were comfortable reaching out to the group as a whole for clarification. This type of internal communication prevented any significant internal team conflicts or roadblocks. Most of the "challenges" we faced as a team were external or project-based, rather than interpersonal between members. These included the technical understanding of the Edge Impulse output, the complex task of code integration for the ESP32, adapting our model from NPK data to EC/moisture sensor inputs, and, as discussed earlier, navigating the somewhat competitive inter-team dynamic within the course.

## ***E. Accomplishments***

Despite the complex nature of the project, our team reached several key achievements that we were proud of. The primary success of the project was developing a highly accurate TinyML model within Edge Impulse. Our team worked to improve the model's performance, increasing its accuracy of around 82% to a final figure exceeding 94% through constant data validation and classification.  
Crucially, we demonstrated adaptability by successfully re-engineering our modeling approach. When confronted with the initially provided NPK-based dataset and the actual capabilities of our onboard sensors, we effectively created, trained, and validated a new model explicitly tailored to the hardware we had at hand, which was a vital achievement that guaranteed the practical viability of our project.  
The culmination of these efforts was creating a functional, integrated system. We achieved our primary technical objective of deploying this adapted, high-accuracy model onto the LILYGO T-Higrow board. Furthermore, we successfully integrated this model with the existing ESP DASH firmware, enabling the device to display real-time sensor readings and the resulting soil health predictions on its web dashboard. The successful flashing of the complete working Arduino project onto the ESP32 and seeing it function as designed defined the team’s most significant accomplishment.

# **V. Alignment of Expectations and Actions**

Reflecting on the SolarSPELL course involves comparing my initial expectations and personal hopes against the actual experiences and outcomes.

## ***A. How did the course correspond to my expectations?***

My primary expectation when the course was just starting was to be significantly involved in a project culminating in a fully developed and functional TinyML model capable of telling users how healthy the soil was and how to fix it if the soil was not healthy. I expected a hands-on experience that would allow me to move beyond theoretical knowledge into the practical application of machine learning on microcontrollers. I had experience with machine learning and wanted to push my knowledge further and apply it to a tangible and worthwhile cause.  
Upon reflection, the course met these core expectations. We successfully developed and flashed a working TinyML model onto the LILYGO T-Higrow board, which was the central technical aspiration I held for the course. The project-based nature of the curriculum demanded direct engagement with hardware and software development tools and machine learning pipelines. It aligned perfectly with my anticipation of a practical, hands-on learning environment. The "noble effort" aspect of the SolarSPELL initiative, aiming to create practical ways for those in countries lacking resources, also resonated with my expectation of working on something with potential real-world applicability. The slightly siloed inter-team dynamic was the only element that differed somewhat from unstated expectations. I had not assumed we would be as separated as we were, and would be more openly collaborative across the entire course session.

## ***B. How did my actions correspond to my hopes for the course?***

My actions throughout the semester corresponded directly with my hopes for the course. I had hoped to take on a significant technical challenge, and my focused responsibility for integrating the Edge Impulse model with the ESP32's firmware and the ESP DASH dashboard certainly fulfilled this. My intensive effort in understanding the separate codebases, debugging the integration issues, and ultimately bringing the system to life addressed my desire to create a tangible, working TinyML application.  
Furthermore, I had significantly developed my skills in programming, working effectively with external libraries, and understanding the practicalities of machine learning deployment on resource-constrained devices. My actions in tackling the integration task head-on, including leveraging AI tools like Google Gemini for problem-solving, directly contributed to achieving these personal development goals. The successful outcome of this work provided a strong sense of achievement. It verified that my efforts aligned with my aspirations for enhancing my skills and meaningful project contribution.

# **VI. Conclusion**

The course and the final project to develop a TinyML-driven soil analysis tool delivered a rich and multifaceted learning experience. This paper has detailed my journey within this initiative, highlighting my contributions to integrating an Edge Impulse model with the LILYGO T-Higrow sensor and ESP DASH, reflecting on the functional dynamics of our team and the entire class, and offering a personal assessment of the course's strengths and potential areas for improvement.  
Key learnings from this experience are numerous. Practically, I gained invaluable insights into deploying TinyML models on microcontrollers, including the iterative process of model adaptation to available hardware. The project also underscored the noteworthy challenges and enormous satisfaction in system integration, particularly when bridging machine learning outputs with embedded system firmware and user interfaces. Another critical takeaway was the importance of clear, consistent communication and shared situational leadership in a large student team.  
Overall, the final project was a challenging yet gratifying experience. It offered a valuable opportunity to apply my limited knowledge to a tangible problem with real-world implications. Developing the soil health prediction model underscored the huge potential of combining accessible machine learning tools with affordable hardware to create impactful, locally deployable solutions. This experience heightened my interest in embedded AI and its applications, providing a strong foundation of practical skills and collaborative insights that I will carry into future endeavors.