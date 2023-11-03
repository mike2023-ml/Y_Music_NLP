# <div align='center'>👋 Вас приветствует Команда №2 - *"SoundCheck"*!</div>

### Хакатон DS Яндекс.Музыка - Сопоставление текстов музыкальных произведений и поиск каверов по их текстам

**Цель проекта:**  
Улучшение качества рекомендаций музыкального сервиса путем точного определения и классификации каверов.

😀 **Состав команды и роли:**  
* Никифорова Юлия - PM &nbsp;&nbsp;&nbsp;(<img src="https://github.com/mike2023-ml/Portfolio/assets/116313032/d3f08c03-7dec-490e-ad39-75152295c4d5" title="Telegram" alt="Telegram" width="20" height="20"/>@Niki_for_Ova)
* Прозоров Кирилл - DS &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<img src="https://github.com/mike2023-ml/Portfolio/assets/116313032/d3f08c03-7dec-490e-ad39-75152295c4d5" title="Telegram" alt="Telegram" width="20" height="20"/>@prozorovpro)
* Куликова Екатерина - DS &nbsp;(<img src="https://github.com/mike2023-ml/Portfolio/assets/116313032/d3f08c03-7dec-490e-ad39-75152295c4d5" title="Telegram" alt="Telegram" width="20" height="20"/>@EkaterinaTretia)
* Егоров Михаил - DS&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<img src="https://github.com/mike2023-ml/Portfolio/assets/116313032/d3f08c03-7dec-490e-ad39-75152295c4d5" title="Telegram" alt="Telegram" width="20" height="20"/>@mikenonstop)

***

**Ссылка на проект:**  
[`ipynb`](https://github.com/EkaterinaIII/Y_Music_NLP/blob/main/y_music.ipynb)  

**Если проект не открывается, его можно просмотреть по этой ссылке:**  
[`nbviewer`](https://nbviewer.org/github/EkaterinaIII/Y_Music_NLP/blob/main/y_music.ipynb)

***

### 🔥 Этапы исследования:

| № | Гипотезы       | Задачи                | Выводы |
|:--:| :-------------: |:------------------:| :-----:|
|1| По метаданным трека можно определить оригинал или не оригинал. | Классификация оригинал/кавер. | В результате использования разных подходов к подбору признаков для обучения модель CatBoostClassifier показала хорошие результаты при решении задачи классификации оригинал/кавер.  <br>**`CatBoostClassifier, Sklearn, F1-score, Matplotlib`**|
|2| На основании текстов треков можно определить, связаны ли треки между собой или нет.| Определение "связанности" треков. | Гипотеза о том, что на основании текстов можно определить связаны ли треки, подтвердилась.  <br>**`CatBoostClassifier, Sklearn, F1-score`**|
|3| Для каждого заданного трека (не важно, дан кавер или оригинал) возможно найти все связанные с ним, имеющиеся в базе (группа - все каверы на одну и ту же песню , включая саму песню). | Поиск связных треков после векторизации и кластеризации. | Изменяя порог, можно регулировать соотношение полноты и кол-ва набора "лишних треков", взависимости от целей. <br>**`LaBSE , Sklearn, NumPy, Scipy`**|
|4| При наличии достаточного количества реальных данных о годе студийной записи, оригиналом среди подобранных похожих треков, будет композиция с наиболее ранней датой издания (кавер не может появиться до фактического издания оригинала). | Определить среди подобранных похожих треков оригинал. | Имея точные данные о дате издания аудиозаписи возможно выбрать оригинал среди похожих композиций. |

***

### :hammer_and_wrench: Стек использованных технологий:  

<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/python/python-original.svg" title="Python" alt="Python" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/pandas/pandas-original-wordmark.svg" title="Pandas" alt="Pandas" width="40" height="40"/>&nbsp;  
  <img src="https://github.com/devicons/devicon/blob/master/icons/jupyter/jupyter-original-wordmark.svg" title="Jupyter" alt="Jupyter" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/github/github-original-wordmark.svg" title="Github" alt="Github" width="40" height="40"/>&nbsp;
  <img src="https://github.com/mike2023-ml/Portfolio/assets/116313032/732a89ba-9ba9-4003-91c3-c9f47a63db25" title="Сatboost" alt="Сatboost" width="40" height="40"/>&nbsp;
  <img src="https://github.com/mike2023-ml/Portfolio/assets/116313032/ce1045c0-189d-4405-bf32-eb9b0ad42ddd" title="Matplotlib" alt="Matplotlib" width="40" height="40"/>&nbsp;
  <img src="https://github.com/scipy/scipy/blob/main/doc/source/_static/logo.svg" title="Scipy" alt="Scipy" width="40" height="40"/>&nbsp;
  <img src="https://github.com/mwaskom/seaborn/blob/master/doc/_static/logo-mark-darkbg.svg" title="Seaborn" alt="Seaborn" width="40" height="40"/>&nbsp;
  <img src="https://github.com/scikit-learn/scikit-learn/blob/main/doc/logos/scikit-learn-logo-notext.png" title="Scikit-learn" alt="Scikit-learn" width="60" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/pytorch/pytorch-original.svg" title="Pytorch" alt="Pytorch" width="40" height="40"/>&nbsp;
</div>

***

### Итоговый вывод:

Таким образом, при решении задачи классификации по метрике **F1-score** лучшей моделью мы выбрали **CatBoostClassifier**. При решении задачи поиска связанных треков на основании близости друг с другом эмбеддингов предложений с одинаковым смыслом на разных языках по метрике **Recall** лучшей моделью мы выбрали **LaBSE**.


В рамках данного хакатона были выполнены все поставленные организаторами задачи, а также предложено и протестировано несколько дополнительных гипотез.  
При сопоставлении каверов и оригиналов по их текстам мы заметили, что наша модель находит не все треки, а около 70-90%, в зависимости от настроек порога, что довольно неплохо, но мы решили подробно изучить группы треков с самой плохой метрикой. 

Мы выявили несколько причин:
- Междометья/неполный текст кавера: **предлагаемое решение:**
  - сделать суммаризацию текстов;
  - убрать лишние повторяющиеся междометья (или заменить одним);
  - учитывать дополнительным признаком расстояния между векторизованными предварительно суммаризованными текстами.
- Ошибки разметки: **предлагаемое решение:**
  - для заполнения текстов песен использовать не парсинг с различных сайтов, а предобученные модели по распознаванию речи.


