End-to-end implementation process of a MLP model using NLP

-- The purpose of this project was not to necessarily get powerful prediction results using NLP. Instead the focus was on
whether or not it had potential. 

Throughout the last few years there has been notable progress predicting a patients hospital
length of stay (LOS) as predictive methods become inepter to process health records. However,
there is still no concrete solution, leaving physicians to predict LOS based on their experience.
The longer healthcare goes without a resolution to effectively predict LOS, the more issues persist
such as shortage in labor, bed resources, financial loss, and other expense [1]. Therefore,
creating a competent model to accurately predict LOS is crucial because it has the potential to
provide impactful insights and access to new information into overhead and direct costs, patient
flow and resource management, room for improvements, and even overlooked nuances.
Therefore, the mission was to develop and evaluate a machine learning model that can accurately
predict patients’ hospital LOS using Natural Language Processing (NLP). NLP can go beyond
traditional methods by finding meaningful patterns in clinical details about a patient’s admission.
These relationships can be reason for admission, diagnoses, type of insurance – all which
influence a patients LOS.
The goal was to use numeric embeddings obtained with BioBERT to capture clinical relationships
from unstructured data and understand what those variables mean prior to training a prediction
model. Versus the use of traditional tabular data that doesn’t know meaning before training and
only uses numbers to find patterns and relationships.
The process used PostgreSQL to pipeline engineer a structured master dataset using the most
influential patient admission data from a publicly available clinical database called MIMIC-III. The
structured data was transformed into natural language clinical text summaries using a Large
Language Model(LLM). These summaries were then numerically encoded with BioBERT
embeddings - a pre-trained biomedical language. Resulting in numeric vectors, which served as
the inputs to a Multi-Layer Neural Network Classification Model to predict patients’ length of stay
within a range of 1- 7+ days.

Results:
Overall, the model struggled to categorize across 8 classes, with ~16% test accuracy. However,
when considering binary classes (short stay vs long stay) instead of the more granular 8 class,
performance improved to ~60% test accuracy. Yet the traditional tabular input still outperformed
with a test accuracy of ~81%. Results suggest that models using NLP to predict LOS, have the
potential. Still, it is not enough evidence to confidently say if it’ll be successful or not. Arguably,
with the promising binary results, it is sufficient enough to continue exploring LOS predictions
using NLP. If one can be successfully created, it can be transformative to the healthcare industry.
