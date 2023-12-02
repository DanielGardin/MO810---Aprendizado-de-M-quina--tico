---

---






# Model Card for CrimeDescriber_XGBoost

<!-- Provide a quick summary of what the model is/does. [Optional] -->
Esse modelo tem como objetivo realizar uma classificação binária das regiões de São Paulo como perigosas ou não perigosas e oferecer explicabilidade.




#  Table of Contents

- [Model Card for CrimeDescriber](#model-card-for--model_id-)
- [Table of Contents](#table-of-contents)
- [Table of Contents](#table-of-contents-1)
- [Model Details](#model-details)
  - [Model Description](#model-description)
- [Uses](#uses)
  - [Direct Use](#direct-use)
  - [Downstream Use [Optional]](#downstream-use-optional)
  - [Out-of-Scope Use](#out-of-scope-use)
- [Bias, Risks, and Limitations](#bias-risks-and-limitations)
  - [Recommendations](#recommendations)
- [Training Details](#training-details)
  - [Training Data](#training-data)
  - [Training Procedure](#training-procedure)
    - [Preprocessing](#preprocessing)
    - [Speeds, Sizes, Times](#speeds-sizes-times)
- [Evaluation](#evaluation)
  - [Testing Data, Factors & Metrics](#testing-data-factors--metrics)
    - [Testing Data](#testing-data)
    - [Factors](#factors)
    - [Metrics](#metrics)
  - [Results](#results)
- [Model Examination](#model-examination)
- [Environmental Impact](#environmental-impact)
- [Technical Specifications [optional]](#technical-specifications-optional)
  - [Model Architecture and Objective](#model-architecture-and-objective)
  - [Compute Infrastructure](#compute-infrastructure)
    - [Hardware](#hardware)
    - [Software](#software)
- [Citation](#citation)
- [Glossary [optional]](#glossary-optional)
- [More Information [optional]](#more-information-optional)
- [Model Card Authors [optional]](#model-card-authors-optional)
- [Model Card Contact](#model-card-contact)
- [How to Get Started with the Model](#how-to-get-started-with-the-model)


# Model Details

## Model Description

<!-- Provide a longer summary of what this model is/does. -->
Esse modelo tem como objetivo realizar uma classificação binária das regiões de São Paulo como perigosas ou não perigosas e oferecer explicabilidade. Buscamos responder à pergunta: dada uma região com características socio-econômicas x, qual a probabilidade de amostrarmos os mesmos boletins de ocorrência que foram coletados dada a distribuição condicionada a x?


- **Developed by:** Aline C.C. S. Azevedo, Beatriz C. Nascimento, Daniel G. Gratti
- **Shared by [Optional]:** More information needed
- **Model type:** Supervised, Decision Trees, Tabular
- **Language(s) (NLP):** pt
- **License:** bsd-3-clause
- **Library Name:** sklearn



# Uses
Este modelo tem como objetivo de uso a determinação de quais características socioeconômicas de uma dada região de São Paulo são mais influentes na classificação de um local como perigoso ou não perigoso.  
<!-- Address questions around how the model is intended to be used, including the foreseeable users of the model and those affected by the model. -->

## Direct Use
Este modelo foi desenvolvido para uso exclusivo de análise estatística de correlação entre diferentes características de determinada região em sua segurança, e seu escopo de uso é o acadêmico.
<!-- This section is for the model use without fine-tuning or plugging into a larger ecosystem/app. -->
<!-- If the user enters content, print that. If not, but they enter a task in the list, use that. If neither, say "more info needed." -->



## Out-of-Scope Use
Este modelo não deve ser utilizado fora do contexto acadêmico, não deve ser decisivo em instauração de políticas públicas de segurança. Além disso, ele foi treinado para o contexto da cidade de São Paulo.
<!-- This section addresses misuse, malicious use, and uses that the model will not work well for. -->
<!-- If the user enters content, print that. If not, but they enter a task in the list, use that. If neither, say "more info needed." -->


# Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->
Utilizamos um parâmetro k que controla a quantidade mínima de boletins de ocorrência para classificar uma região como "perigosa". A escolha desse threshold pode introduzir vieses no modelo. 

## Recommendations

<!-- This section is meant to convey recommendations with respect to the bias, risk, and technical limitations. -->
O modelo não deve ser utilizado fora do contexto acadêmico. O parâmetro k deve ser escolhido de forma crítica, por meio de uma análise de fatores sociais e econômicos da região a ser estudada. O modelo não deve ser utilizado fora do contexto da cidade de São Paulo.



# Training Details

## Training Data
https://github.com/DanielGardin/MO810-Ethical-Machine-Learning/tree/master/T2%20-%20Tratamento%20de%20dados%2C%20vi%C3%A9ses%20e%20privacidade/Tropa%20mrai
Nesse base de dados, estão presentes dados socioeconômicos de diversas regiões de São Paulo, assim como informações relacionadas a segurança como a quantidade de boletins de ocorrência por região.
<!-- This should link to a Data Card, perhaps with a short stub of information on what the training data is all about as well as documentation related to data pre-processing or additional filtering. -->


## Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

### Preprocessing
Durante o pré processamento, fizemos engenharia de features para gerar o target. Além disso, normalizamos os dados e realizamos one hot encoding nas variáveis categóricas. 

 
# Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

## Testing Data, Factors & Metrics

### Testing Data

<!-- This should link to a Data Card if possible. -->

https://github.com/DanielGardin/MO810-Ethical-Machine-Learning/tree/master/T2%20-%20Tratamento%20de%20dados%2C%20vi%C3%A9ses%20e%20privacidade/Tropa%20mrai


### Factors

<!-- These are the things the evaluation is disaggregating by, e.g., subpopulations or domains. -->
A entrada do modelo é padronizada conforme os dados censitários das regiões de São Paulo. O modelo não generaliza para outras regiões devido a um possível desvio de distribuição.



### Metrics

<!-- These are the evaluation metrics being used, ideally with a description of why. -->

Acurácia balanceada - é utilizada para entender a performance geral do modelo
ROC AUC - é utilizada para analisar a performance do modelo para diversos threshold simultaneamente, obtendo informações mais diversas que a acurácia balanceada
Brier Score - é utilizada para medir a calibração do modelo e garantir confiança na predição



# Model Examination

O principal foco desse modelo é a explicabilidade. Ao determinar quais características socioeconômicas são mais relevantes para a determinação de uma região como perigosa ou não, podemos entender quais problemas sociais estão influenciando negativamente no comportamento criminal de certo ambiente.



# Model Card Authors [optional]

<!-- This section provides another layer of transparency and accountability. Whose views is this model card representing? How many voices were included in its construction? Etc. -->
Aline C.C. S. Azevedo, Beatriz C. Nascimento, Daniel G. Gratti


# Model Card Contact
a189593@dac.unicamp.br, b247403@dac.unicamp.br, d214729@dac.unicamp.br


