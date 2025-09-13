## ДЗ №1
Задача: бинарная классификация (по признакам клиента понять, можно ли данному клиенту давать займ)
Метрика: ROC-AUC. Для каждого эксперимент логировать график loss'а и метрики на train'е и на test'е.

## Эксперимент 1. Простая модель
Архитектура
Простой блок
1. Linear (hidden size в hidden size * 4)
2. ReLU
3. Linear (hidden size * 4 в hidden size)
Параметры
hidden size = 32
SGD c lr = 0.01
количество эпох = 10
batch size = 32
### Эксперимент 2. Модель побольше: 3 простых блока, hidden size = 128
### Эксперимент 3. Skip Connections, Batch Norms: Добавлен Skip Connection от входа блока к его выходу, а также Batch Norm в начале каждого блока
### Эксперимент 4. Dropout: Добавлен dropout внутрь блока и подобран оптимальный p для него (можно среди 0.01, 0.1, 0.2, 0.5, 0.9)
### Эксперимент 5. Weight Decay, Learning Rate: Включен weight decay и подобрана оптимальная пара: lambda для weight decay=(0.1, 0.01, 0.001) и оптимальный learning rate=(0.01, 0.05, 0.1).

## ДЗ №2
Есть обученный Transformer Decoder. 
Задача: Реализовать разные способы генерации текста для заранее обученного Transformer Decoder.

Создать экземпляр модели и токенизатора при помощи библиотеки transformers:
from transformers import AutoModelForCausalLM, AutoTokenizer
model = AutoModelForCausalLM.from_pretrained('Qwen/Qwen2.5-0.5B-Instruct').eval()
tokenizer = AutoTokenizer.from_pretrained('Qwen/Qwen2.5-0.5B-Instruct')

### Задача 1. Greedy Decoding



