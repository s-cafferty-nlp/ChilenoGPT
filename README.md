# ChilenoGPT

### This is just a fun project to create a text generation model that uses colloquial Chilean Spanish.

## Data Collection

### The most challenging part of this project is certainly the data collection process. It is quite difficult to find text data that reflects colloquial Chilean Spanish. Indeed, although some linguist-oriented corpora exist, their format is not ideal. As such, I resorted to scraping several thousand comments from r/Chile Reddit threads. This text, though somewhat slapdash, no doubt reflects colloquial Chilean Spanish in terms of style and diction. Moreover, this text reflects the ways in which Chileans use their language on the internet. Though this resource is limited in scope, it's a great baseline for finetuning a model to reflect a low-resource dialect.

## Methods

### It behooves us to take advantage of byte-pair tokenization if we want to include a lot of the texture that makes Chilean Spanish unique. As such, this project uses Huggingface to finetune a GPT2 model to generate Chilean Spanish from a piece of 'starter text'. The hyperparameters were then chosen via a gridsearch approach with human feedback. [The model was trained in this notebook.](www.w)

## Results

### The content itself isn't always logical, frankly. But it's no doubt very Chilean in its presentation. In the sample text below, we see how the model is able to elaborate on starter text in a way that mirrors the behavior of Chilean redditors. The model certainly seems to contain information about Chilean politics and prejudices. Overall, it's rather charming the extent to which the model uses particular chilenismos such as 'la raja' and 'weón' with ease.

```

INPUT: Santiago es una ciudad
HPARAMS: top_k = 20 ,temp = 0.8, penalty = 1.0, top_p = 0.95

OUTPUT:
Santiago es una ciudad mala y uno de los que se me hacen cagar en la calle.
Pero si el weon de los que andan haciendo cagar en la calle, es mala,
y lo de los que hacengan en la calle son unos wnes, en el mochila que hacen.
Y de todo eso a las weas se le da unos pikachu
Es el mismo que los pikachu, lo de los que le dicen los pikachu.
Y de los que son los pikachu, es el mismo que los pikachu.
Es el mismo que también también pikachu.
Y si pikachu es el mismo que pikachu
Pikachu es el mismo que te da pikachu y pikachu
Pikachu es el mismo que pikachu en tu cama, es el mismo que también pikachu.

INPUT: Yo creo que Boric
HPARAMS: top_k = 50 ,temp = 0.8, penalty = 1.1, top_p = 0.5

OUTPUT:
Yo creo que Boric no tiene nada de malo.
Espero decirle que es una wea más fome, porque el wn va a ser peor que la gente y los pacos en general?
Es como lo hace con la derecha mas difícil que se veia bien llorar. Y yo soy pobre pero estoy siempre
mejor para tener fifa y leerlo pa la otra opción. No te guste ni hablar delinche, solo quieren todo si
las personas viven en su casa cuando salen alguienes cerca, quizás hay que ya son asqueros qliao.
También tenemos que desaparecido hasta el día y nos llegamos a ver siendo "el presidente" xd. P
ero ahora nunca hemos trabajado mucho igual... Yo digo que sea bueno saber tu punto, entonces.

```

## Further Research

### In its present form, ChilenoGPT is certainly fun, but it doesn't serve a particular business logic as of yet. Even so, this project could be improved by some involved approaches to data augmentation. Namely, would an encoder-decoder model allow us to transform this data into a question-answer format (e.g. a model to create questions based on 'response' text that we already have)? With a few hundred labeled examples, this might well be feasible. Moreover, GPT2 is kind of passé at this point. Finetuning a bigger model may produce better results. Such an approach might allow us to convert our text-generator into a Chilean-speaking chatbot. Stay tuned for updates!
