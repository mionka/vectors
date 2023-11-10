# vectors

### [POTRACE](https://potrace.sourceforge.net)
Распространяется в основном в виде пакета, который надо установить себе на компьютер. Открытое и бесплатное. С цветными картинками не работает вообще, для использования нужно исходное изображение предварительно преобразовать в бинарное. Очень хорошо сглаживают изображение, при этом не теряя важные детали (по типу углов). Работает через выделение контуров. Только кривые Безье. Подробное описание алгоритма [тут](https://potrace.sourceforge.net/potrace.pdf).

<img src="https://github.com/mionka/vectors/blob/main/images/vector_images/potrace_1.svg" width="250" />

### [RECRAFT](https://app.recraft.ai)

Генерит картинки сразу заполненными, послойно.

Переводит картинку нормально: здесь например, в самом низу "лицо", а поверх него уже рисуются детали лица. Все через Кривые Безье. Также используется градиент!!! 

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/recraft/vectorize/cute-smiling-emoji.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/recraft/vectorize/cute-smiling-emoji.svg" width="250" />
</p>

Здесь потерял одну деталь (серый круг):

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/recraft/vectorize/yin-yang-simple.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/recraft/vectorize/yin-yang-simple.svg" width="250" />
</p>

**Оригинальные картинки для следующих решений можно посмотреть [здесь](https://github.com/mionka/vectors/tree/main/images/orig_images), а результаты — [здесь](https://github.com/mionka/vectors/tree/main/images/vector_images)**


### [VECTORIZER.IO](https://www.vectorizer.io)
Есть сайт, можно скачать только одну картинку бесплатно, доступ через API не предусмотрен, решение норм, но цвета ИНОГДА слишком блеклые (для ярких исходных картинок).

Не очень качественно. Для изображений, состоящего исключительно из фигур, не смог сделать ровные линии:

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vectorizer_io_1.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vectorizer_io_2.png" width="250" />
</p>

Для более сложного изображение качество в разы хуже: 

<img src="https://github.com/mionka/vectors/blob/main/images/res_details/4_vectorizer_io_1.png" width="350" />

Также на примере смайлика:

<img src="https://github.com/mionka/vectors/blob/main/images/vector_images/smiley_vectorizer_io.png" width="350" />

Результат выглядит неплохо, но при приближении видны проблемы: много лишних фигур.

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/smiley_vectorizer_io_1.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/smiley_vectorizer_io_2.png" width="250" />
</p>

Внутрь посмотреть не удалось, не дает скачать.

### [VECTORIZER.AI](https://vectorizer.ai)
Есть сайт с бета-версией (бесплатное использование), доступ через API есть, но платный (можно купить не более 100_000 обращений в месяц). Норм решение, но переходы резкие.  оч хорошее решение, но иногда работает странно.


Очень хорошо обрабатывает простые фигуры (особенно по сравнению с предыдущим решением):

<img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vectorizer_ai_1.png" width="500" />

<img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vectorizer_ai_2.png" width="500" />

С более сложный изображением справилось лучше, чем предыдущее решение, но, я думаю, некоторые объекты все еще можно опустить (слишком подробный результат). В некоторых моментах все еще не очень качественно и ровно.

<img src="https://github.com/mionka/vectors/blob/main/images/res_details/4_vectorizer_ai_1.png" width="500" />


Если заглядывать внутрь, то выглядит есть интересная деталь: рисуются фигуры (path fill), а затем "дыры" между фигурами закрашиваются с помощью линий (path strokes). Некоторые фигуры распознаются как реальные геометрические фигуры (ellipse, ...), но так происходит не всегда (если отправить несколько картинок с эллипсами, то некоторые из них не распознаются как эллипс).

После удаления всех <path fill ...\> может получиться нечто подобное:

<img src="https://github.com/mionka/vectors/blob/main/images/res_details/4_vectorizer_ai_nofill.svg" width="500" />

После удаления <path stroke ...\> появляются пробелы (пробелы на первом изображении):

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/vectorizer_ai_holes.png" width="400" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/vectorizer_ai_no_holes.png" width="400" />
</p>


### [VECTOR MAGIC](https://ru.vectormagic.com)
Есть сайт + десктопное приложение, обе версии платные (перевести можно, скачать нет), доступа через API нет, оч хорошее решение, но иногда работает странно.

Очень хорошо обрабатывает простые фигуры:

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vector_magic_1.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vector_magic_2.png" width="250" />
</p>

Однако для более сложного изображения результат может быть искаженный (не для всех, на некоторых работает отлично):

<img src="https://github.com/mionka/vectors/blob/main/images/vector_images/4_vector_magic.png" width="500" />

### [VTRACER](https://github.com/visioncortex/vtracer)

Позволяет векторизовать цветные картинки. Описание алгоритма [тут](https://www.visioncortex.org/vtracer-docs).

Неплохо обрабатывает простые фигуры, очень хорошо сглаживает неровности, но иногда из-за этого может потеряться какая-то деталь, некоторые неровности иногда также остаются.

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vtracer_1.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vtracer_2.png" width="250" />
</p>

Чем сложнее изображение, тем ниже качество:

<img src="https://github.com/mionka/vectors/blob/main/images/res_details/4_vtracer.png" width="500" />

Везде использует Безье. Фигуры в результате накладываются друг на друга, например (удалили тень на руке):

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/4_vtracer_before.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/4_vtracer_after.png" width="250" />
</p>

Также пример со смайликом:

<img src="https://github.com/mionka/vectors/blob/main/images/vector_images/smiley_vector_magic.png" width="500" />

Изображение в целом выглядит неплохо, но при приближении видны проблемы:

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/smiley_vector_magic_1.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/smiley_vector_magic_2.png" width="250" />
</p>



### [VECTORMAKER](https://vectormaker.co)

Использует potrace; цвет, но вручную выбираешь количество цветов(?шагов). При этом иногда предложенных цветов недостаточно.

ОЧЕНЬ долгий. Работает следующим образом: сначала зарисовывает все изображение одним цветом (шаг 1), потом на каждом шагу часть ЗАКРАШЕННЫХ УЖЕ!!! деталей перекрашивает (поверх):

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vectormaker_step_1.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vectormaker_step_2.png" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/res_details/1_vectormaker_step3.png" width="250" />
</p>

Для некоторых изображений предложенных цветов недостаточно:

<img src="https://github.com/mionka/vectors/blob/main/images/vector_images/4-vectormaker-co.svg" width="500" />

Также пример со смайликом. По умолчанию рисуется с 6 цветами, результат неплохой, но теряются детали (на мой взгляд, достаточно важные). При увеличении количества цветов становится больше деталей, но изображение становится не очень качественным.

<p float="left">
  <img src="https://github.com/mionka/vectors/blob/main/images/vector_images/smiley_vtracer_6col.svg" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/vector_images/smiley_vtracer_7col.svg" width="250" />
  <img src="https://github.com/mionka/vectors/blob/main/images/vector_images/smiley_vtracer_8col.svg" width="250" />
</p>

Второй результат мог бы быть неплохим, если бы был чуть менее кривым:( Так-то он неплохой
