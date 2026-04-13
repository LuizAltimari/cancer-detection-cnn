# cancer-detection-cnn
Atividade para a Disciplina de Inteligência Artificial para Devs no curso de Análise e Desenvolvimento de Sistemas da UNESA.

# Descrição

Este projeto tem como objetivo classificar imagens médicas em duas categorias:

0 → Negativo (sem câncer)
1 → Positivo (com câncer)

Foi desenvolvida uma CNN simples, porém eficiente, capaz de atingir aproximadamente 95% de acurácia no conjunto de teste.

# Dataset
Total de imagens: 2942
Treinamento: 2206 imagens
Teste: 736 imagens
Divisão: 75% treino / 25% teste

As imagens são redimensionadas para:

40x40 pixels (RGB)

# Arquitetura do Modelo

A CNN utilizada possui a seguinte estrutura:

2 camadas convolucionais:
Conv2D (20 filtros) + ReLU + MaxPooling
Conv2D (50 filtros) + ReLU + MaxPooling
Flatten
Dense (500 neurônios) + ReLU
Camada de saída:
Dense (1 neurônio)
Ativação: Sigmoid
⚙️ Tecnologias Utilizadas
Python 3.11
TensorFlow / Keras
NumPy
Scikit-learn
OpenCV
Imutils

# Instalação
1. Criar ambiente virtual
py -3.11 -m venv dl-env
2. Ativar o ambiente

Windows:

.\dl-env\Scripts\activate

Linux/Mac:

source dl-env/bin/activate
3. Atualizar ferramentas
python -m pip install --upgrade pip setuptools wheel
4. Instalar dependências principais
pip install numpy==1.24.3
pip install tensorflow==2.13.1
pip install imutils==0.5.4
5. Instalar demais dependências
pip install -r requirements.txt
# Treinamento
hist = modelo_cnn.fit(aug.flow(x_treino, y_treino, batch_size = batch_size), 
                                validation_data = (x_teste, y_teste), 
                                steps_per_epoch = len(x_treino) // batch_size, 
                                epochs = epochs, 
                                verbose = 1)
# Resultados
Accuracy: 95%
Classification Report:
              precision    recall  f1-score   support

           0       0.95      0.95      0.95       369
           1       0.95      0.95      0.95       367

    accuracy                           0.95       736

