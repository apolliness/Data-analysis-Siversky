## Описание проекта
В рамках дисциплины “Анализ данных и моделирование в урбанистике” студенты 2 курса магистратуры по направлению “Цифровая урбанистика” Института Дизайна и Урбанистики Университета ИТМО выполнили итоговый проект по развитию территории, представив 3 гипотезы ее развития.

Территория исследования и проектирования расположена в границах упраздненного (от 13 мая 2024) Сиверского городского поселения. Входит в Гатчинский муниципальный округ Ленинградской области. Бывший административный центр — городской посёлок Сиверский. Площадь территории составила 13,74 кв. км. Численность населения - 17 275 чел. (2023 г.)
Территориальная доступность оценивается: до Гатчины - 30 км (45 мин на автомобильном транспорте); до Санкт-Петербурга - 68 км (1 час 30 мин на автомобильном транспорте).

## Цель проекта
Цель проекта заключается в разработке и обосновании трех гипотез по развитию проектной территории с учетом применения методов анализа данных и моделирования для их оценки, а также выборе наиболее оптимальной гипотезы для дальнейшей реализации. 

## Гипотезы развития
Гипотезы развития территории предполагают:
- Развитие преимущественно жилой застройки территории с разнообразными сервисами.
- Изменение планировки и характеристики жилой застройки: введение блокированной застройки и индивидуального жилищного строительства (ИЖС).
- Преобразование территории в промышленную, без планов на жилую застройку и развитие сервисов.

## Информация о команде
Работу выполнили студенты 2 курса магистратуры по направлению “Цифровая урбанистика” Института дизайна и урбанистики Университета ИТМО:

- Пьянкова Екатерина (сбор и подготовка данных, разработка сценария 1)
- Туманова Елизавета (сбор и подготовка данных, разработка сценария 2)
- Гапонова Яна (сбор и подготовка данных, разработка сценария 3)
- Рябошлык Полина (сбор и подготовка данных, оформление репозитория)
- Глушакова Елизавета (сбор и подготовка данных, оформление репозитория)

## Работа с гипотезами

### Нулевой сценарий
Для предварительного анализа проектной территории, расположенной в границах Сиверского городского поселения, были проведены следующие шаги:
1. Отрисовка геометрии границ территории.
   
![Границы территории](https://github.com/apolliness/Data-analysis-Siversky/blob/e5c94e53abdd469ff77ebc6c8665c1061768780f/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/qgis/1.%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B%20%D1%82%D0%B5%D1%80%D1%80%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B8.png)

2. Получение геометрии водных объектов, улично-дорожной сети и железных дорог с помощью библиотеки OSMNX.
   
![Вода, ж/д и дороги](https://github.com/apolliness/Data-analysis-Siversky/blob/66cec1c49c0e888ba14a82ac3d9cdf6a5bf5c165/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/qgis/2.%D0%B2%D0%BE%D0%B4%D0%B0%2C%20%D0%B6%D0%B4%20%D0%B8%20%D0%B4%D0%BE%D1%80%D0%BE%D0%B3%D0%B8.png)

3. Получение слоя городских кварталов с помощью BlocksGenerator. На вход были поданы следующие данные: водные объекты, дороги, железнодорожные пути.

![Кварталы](https://github.com/apolliness/Data-analysis-Siversky/blob/e5c94e53abdd469ff77ebc6c8665c1061768780f/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/qgis/3.%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B0%D0%BB%D1%8B.png)

4. Получение графа улично-дорожной сети по полигону территории с помощью библиотеки IduEdu.

![Граф](https://github.com/apolliness/Data-analysis-Siversky/blob/03b65bda9e205cd78efb955761ab561a8f89d366/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D0%B3%D1%80%D0%B0%D1%84%2C%20%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C%2C%20%D1%81%D0%B2%D1%8F%D0%B7%D0%B0%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C/graph_0.png)

5. Вычисление матрицы доступности и матрицы связанности на основе предварительно полученного графа улично-дорожной сети.
   
- Матрица доступности:

![Доступность](https://github.com/apolliness/Data-analysis-Siversky/blob/03b65bda9e205cd78efb955761ab561a8f89d366/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D0%B3%D1%80%D0%B0%D1%84%2C%20%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C%2C%20%D1%81%D0%B2%D1%8F%D0%B7%D0%B0%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C/Accessibility_0.png)

Площадь территории маленькая, поэтому среднее медианное значение от одного квартала до другого будет равняться 10-15 минут.

- Матрица связанности:

![Связанность](https://github.com/apolliness/Data-analysis-Siversky/blob/03b65bda9e205cd78efb955761ab561a8f89d366/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D0%B3%D1%80%D0%B0%D1%84%2C%20%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C%2C%20%D1%81%D0%B2%D1%8F%D0%B7%D0%B0%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C/Connectivity_0.png)

6. Получение данных по зданиям и сервисам для проектной территории с помощью библиотеки OSMNX и расчет обеспеченности для каждого типа сервиса: школы, поликлиники, автобусные остановки, банки, пекарни, детские сады.
   
- Обеспеченность школами исследуемой территории

![Школы](https://github.com/apolliness/Data-analysis-Siversky/blob/838b32c502511ade30de5bbb8d0dc31c3087b53d/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D0%BE%D0%B1%D0%B5%D1%81%D0%BF%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C%20%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%B0%D0%BC%D0%B8/school_0.png)

- Обеспеченность поликлиниками исследуемой территории

![Поликлиники](https://github.com/apolliness/Data-analysis-Siversky/blob/838b32c502511ade30de5bbb8d0dc31c3087b53d/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D0%BE%D0%B1%D0%B5%D1%81%D0%BF%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C%20%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%B0%D0%BC%D0%B8/polyclinic_0.png)

- Обеспеченность детскими садами исследуемой территории

![Детские сады](https://github.com/apolliness/Data-analysis-Siversky/blob/838b32c502511ade30de5bbb8d0dc31c3087b53d/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D0%BE%D0%B1%D0%B5%D1%81%D0%BF%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C%20%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%B0%D0%BC%D0%B8/kindergarten_0.png)

7. Подсчет разнообразия сервисов, центральности кварталов (центральность населения, центральность сервисов), определение типа землепользования (LandUse) и морфотипа застройки (метрика SpaceMatrix).

- Сервисное разнообразие исследуемой территории

![[Разнообразие](https://github.com/apolliness/Data-analysis-Siversky/blob/838b32c502511ade30de5bbb8d0dc31c3087b53d/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D0%BE%D0%B1%D0%B5%D1%81%D0%BF%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C%20%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%B0%D0%BC%D0%B8/services_diversity_0.png)

- Центральность населения

![[Центральность населения](https://github.com/apolliness/Data-analysis-Siversky/blob/838b32c502511ade30de5bbb8d0dc31c3087b53d/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D1%86%D0%B5%D0%BD%D1%82%D1%80%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C/%D1%86%D0%B5%D0%BD%D1%82%D1%80%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C%20%D0%BD%D0%B0%D1%81%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F.png)

- Центральность сервисов

![[Центральность сервисов](https://github.com/apolliness/Data-analysis-Siversky/blob/838b32c502511ade30de5bbb8d0dc31c3087b53d/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/%D1%86%D0%B5%D0%BD%D1%82%D1%80%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C/%D1%86%D0%B5%D0%BD%D1%82%D1%80%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C%20%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BE%D0%B2.png)

- Типы землепользования

![[Землепользование](https://github.com/apolliness/Data-analysis-Siversky/blob/838b32c502511ade30de5bbb8d0dc31c3087b53d/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/LandUse/land_use_0.png)

- Морфотипы застройки

![[Застройка](https://github.com/apolliness/Data-analysis-Siversky/blob/838b32c502511ade30de5bbb8d0dc31c3087b53d/%D0%BD%D1%83%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9%20%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9/SpaceMatrix/SpaceMatrix.png)

### Гипотеза №1
#### Описание
Гипотеза №1 предполагает наличие преимущественно жилой застройки территории с разнообразными сервисами. Для разработки данной гипотезы был использован инструмент rTIM - платформа автоматизированного проектирования развития территории. 

#### Подготовка данных и создание модели территории
Кварталы для территории были отрисованы вручную.

Далее с помощью rTIM были получены параметры жилой застройки и технико-экономические показатели (ТЭП). Спроектированная территория заняла площадь 84,67 га на северо-западе исследуемой территории со следующими ТЭП:
 
Параметр | Значение параметра
--- | --- 
Площадь территории проектирования, га | 84,67
Расчетная численность населения, чел. | 11960
Жилая застройка (включая места общего пользования), м² | 447527,73
Количество общеобразовательных школ | 2
Расчетное количество мест в общеобразовательных школах | 1650
Количество встроенных детских дошкольных учреждений | 11
Расчетное количество мест в детских дошкольных учреждениях | 876
Количество амбулаторно-поликлинических учреждений | 2
Количество посещений амбулаторно-поликлинических учреждений, в смену на 1000 жителей | 420
Площадь зелёных насаждений общего пользования, м² | 8581
Расчетное суммарное количество мест стоянки автомобилей | 1174

Максимальная высота зданий в данном сценарии достигает 9 этажей.

#### Применение методов оценки разработанной территории по гипотезе 1

Были использованы следующие методы оценки территории: 
1. Вычисление матрицы доступности, матрицы связанности на основе графа. 
2. Далее были добавлены планируемые к размещению сервисы и рассчитана обеспеченность для каждого типа сервиса: школы, поликлиники, автобусные остановки, банки, железнодорожные станции, кафе, пекарни, пляжи, детские сады.
3. В результате на основе этих данных был произведен подсчет разнообразия сервисов, центральности кварталов (центральность населения, центральность сервисов), определение типа землепользования (LandUse) и морфотипа застройки (метрика SpaceMatrix).

#### Критерии оценки гипотезы №1 и их интерпретация 

Оценка гипотезы №1 проводилась в сравнении с результатами нулевого сценария (территория без изменений). Для рассмотрения эффективности разработанной гипотезы были применены следующие критерии оценки:

Критерий оценки | Значение для нулевого сценария | Значение для гипотезы №1 | Примечание/интерпретация
--- | --- | --- | --- 
Доступность территории (на основе матрицы доступности) | В диапазоне от 0 до 10 | В диапазоне от 0 до 10 | Добавленные новые кварталы были обеспечены УДС, что оставило неизменным высокий уровень доступности между кварталами
Связанность территории (на основе матрицы связанности) | Варьируется от 0 до 4,5. Центральная часть территории наиболее связана. Запад и восток - менее связаны. | Варьируется от 0 до 4,5. | Разбиение на более мелкие кварталы на северо-западе территории уменьшило показатели на западе - в данной части связанность увеличилась
Обеспеченность территории школами | 0,508 | 0,433 | С значительным увеличением количества жителей обеспеченность школами уменьшилась
Обеспеченность территории детскими садами | 0,400 | 0,367 | С значительным увеличением количества жителей обеспеченность детскими садами уменьшилась
Обеспеченность территории поликлиниками | 0,398 | 0,714 | За счет увеличения количества поликлиник (на 2) значительно повысилась обеспеченность территории
Разнообразие сервисов | В диапазоне от 0 до 2. Центр и северо-запад имеет высокую оценку разнообразности сервисов в качестве их количества и разнородности. | В диапазоне от 0 до 2. Только несколько кварталов в центре имеют высокую оценку разнообразности сервисов в качестве их количества и разнородности | Спроектированная территория из гипотезы 1 снизила оценку разнообразности сервисов из-за уменьшения площади кварталов.
Центральность населения | В диапазоне от 0 до 10. Большая часть населения сконцентрирована на севере и северо-востоке. На северо-западе население - равномерно. | В диапазоне от 0 до 8. Высокая центральность показала, что большая часть населения сосредоточена в небольшом географическом пространстве (в кварталах). | Изменения территории и его заселение жителями увеличило центральность населения, равномерно их распределив. 
Центральность сервисов | В диапазоне от 0 до 0,5. Центральная часть территории имеет наибольший доступ и равномерность распределения сервисов. | В диапазоне от 0 до 0,6. На исследуемой территории оценка центральности сервисов оказалась низкой из-за неравномерности их распределения. | Увеличение количества кварталов напрямую повлияло на неравномерность распределения сервисов.

#### Преимущества и недостатки гипотезы №1

Преимущество гипотезы №1 выражается в размещении большего количества жителей и сервисов на ограниченной территории, что может способствовать экономическому развитию. Размещение сервисов здравоохранения позволило увеличить обеспеченность поликлиниками жителей территории и доступ к данному виду сервиса. Увеличение количества сервисов, в том числе их разнообразия, способно повысить привлекательность территории.

Недостатки гипотезы №1:
- Перегруженность инфраструктуры: Высокая плотность может привести к перегрузке транспортной и социальной инфраструктуры.
- Меньшая комфортность проживания: Высокие здания могут создавать ощущение замкнутости и недостатка зеленых зон.
- Риски для экологии: Увеличение застройки может негативно сказаться на окружающей среде, включая ухудшение качества воздуха и уменьшение зеленых насаждений.

### Гипотеза №2

#### Описание

Разработка второй гипотезы производилась без использования внешних платформ. В этом сценарии изменяются планировка и характеристики жилой застройки: вводится блокированная застройка и индивидуальное жилищное строительство (ИЖС), при этом высота зданий не превышает пяти этажей. 

#### Подготовка данных и создание модели территории
Кварталы, геометрии зданий и дороги были отрисованы вручную.

#### Применение методов оценки разработанной территории по гипотезе №2

Были использованы следующие методы оценки территории: 
1. Вычисление матрицы доступности, матрицы связанности на основе графа. 
2. Далее вручную были добавлены планируемые к размещению сервисы и расчитана обеспеченность для каждого типа сервиса: школы, поликлиники, детские сады, автобусные остановки. 
картинки
3. В результате на основе этих данных был произведен подсчет разнообразия сервисов, центральности кварталов (центральность населения, центральность сервисов), определение типа землепользования (LandUse) и морфотипа застройки (метрика SpaceMatrix).

#### Критерии оценки гипотезы №2 и их интерпретация 

Оценка гипотезы №2 проводилась в сравнении с результатами нулевого сценария (территория без изменений). Для рассмотрения эффективности разработанной гипотезы были применены следующие критерии оценки:

Критерий оценки | Значение для нулевого сценария | Значение для гипотезы №2 | Примечание/интерпретация
--- | --- | --- | --- 
Доступность территории (на основе матрицы доступности) | В диапазоне от 0 до 10 | В диапазоне от 0 до 15 | Дробление незастроенной территории на более мелкие кварталы уменьшило доступность территории на северо-востоке
Связанность территории (на основе матрицы связанности) | Варьируется от 0 до 4,5. Центральная часть территории наиболее связана. Запад и восток - менее связаны | Варьируется от 0 до 4,5. Центральная часть территории наиболее связана. Северо-запад, запад и восток - менее связаны | Увеличение количества кварталов оказало негативное влияние на связанности их с центром.
Обеспеченность территории школами | 0,508 | 0,829 | Неплотная застройка, предполагающая меньшее количество жителей, в совокупности с добавлением новых школ увеличила обеспеченность территории ими, но полностью не закрыла
Обеспеченность территории детскими садами | 0,400 | 0,367 | Неплотная застройка, предполагающая меньшее количество жителей, в совокупности с добавлением новых детских садов увеличила обеспеченность территории ими, но полностью не закрыла
Обеспеченность территории поликлиниками | 0,398 | 1,000 | Увеличение количества поликлиник и изменение характеристик застройки позволило полностью обеспечить территорию сервисом
Разнообразие сервисов | В диапазоне от 0 до 2. Центр и северо-запад имеет высокую оценку разнообразности сервисов в качестве их количества и разнородности. | В диапазоне от 0 до 2. В большей степени кварталы территории имеют низкую оценку разнообразия сервисов. | Спроектированная территория из гипотезы 2 снизила оценку разнообразности сервисов из-за уменьшения площади кварталов.
Центральность населения | В диапазоне от 0 до 10. Большая часть населения сконцентрирована на севере и северо-востоке. На северо-западе население - равномерно. | В диапазоне от 0 до 9. На западе территории неравномерное распределение населения.  | Размещение ИЖС и блокированной застройки повлияло на неравномерное распределение населения на спроектированной территории.
Центральность сервисов | В диапазоне от 0 до 0,5. Центральная часть территории имеет наибольший доступ и равномерность распределения сервисов. | В диапазоне от 0 до 0,5. В новых кварталах оценка варьируется от 0,1 до 0,4, что говорит о неравномерности распределения сервисов. | По результатам внедрения гипотезы 2 в новых кварталах значения центральности сервисов близки к высоким как отражение наибольшего доступа и их равномерности распределения.

#### Преимущества и недостатки гипотезы №2

Преимуществами гипотезы №2 можно отметить:
- Низкая этажность застройки. Данный фактор создает более комфортные условия для проживания, улучшает восприятие территории жителями.
- Учет принципов устойчивого развития: Блокированная застройка и ИЖС могут способствовать более гармоничному развитию территории с учетом существующих ресурсов.

Недостатком гипотезы №2 является меньшая плотность застройки, которая может привести к недостаточному количеству жилья и сервисов для растущего населения.

### Гипотеза №3

#### Описание

Гипотеза №3 существенно отличается от первых двух: в данном сценарии территория преобразуется в промышленную, без планов на жилую застройку и развитие сервисов. 

#### Подготовка данных и создание модели территории
Кварталы и промышленные здания были отрисованы вручную.

#### Применение методов оценки разработанной территории по гипотезе №3

Были использованы следующие методы оценки территории: 
1. Вычисление матрицы доступности, матрицы связанности на основе графа. Также была произведена оценка центральности населения и определение и морфотипа застройки (метрика SpaceMatrix).
картинки

#### Критерии оценки гипотезы №3 и их интерпретация 

Оценка гипотезы №3 проводилась в сравнении с результатами нулевого сценария (территория без изменений). Для рассмотрения эффективности разработанной гипотезы были применены следующие критерии оценки:

Критерий оценки | Значение для нулевого сценария | Значение для гипотезы №3 | Примечание/интерпретация
--- | --- | --- | --- 
Доступность территории (на основе матрицы доступности) | В диапазоне от 0 до 10  | В диапазоне от 0 до 10  | Добавление укрупненных кварталов не повлияло на доступность территории
Связанность территории (на основе матрицы связанности) | Варьируется от 0 до 4,5. Центральная часть территории наиболее связана. Запад и восток - менее связаны. | Варьируется от 0 до 4,5.Центральная часть территории наиболее связана. Запад и восток - менее связаны. | Значения оценки критично не изменились. На северо-западе новые кварталы имеют оценку около 3  
Обеспеченность территории школами | 0,508 | - | Без изменений. В данной гипотезе не предусмотрено добавление сервисов
Обеспеченность территории детскими садами | 0,400 | - | Без изменений. В данной гипотезе не предусмотрено добавление сервисов
Обеспеченность территории поликлиниками | 0,398 | - | Без изменений. В данной гипотезе не предусмотрено добавление сервисов
Разнообразие сервисов | В диапазоне от 0 до 2. Центр и северо-запад имеет высокую оценку разнообразности сервисов в качестве их количества и разнородности. | - | В данной гипотезе не предусмотрено добавление сервисов
Центральность населения | В диапазоне от 0 до 10. Большая часть населения сконцентрирована на севере и северо-востоке. На северо-западе население - равномерно. | В диапазоне от 0 до 10. | Изменения на территориии повлияли на равномерное распределение населения на спроектированной территории.
Центральность сервисов | В диапазоне от 0 до 0,5. Центральная часть территории имеет наибольший доступ и равномерность распределения сервисов. | - | В данной гипотезе не предусмотрено добавление сервисов

#### Преимущества и недостатки гипотезы №3

Преимущества гипотезы №3:
- Простота реализации: Промышленная застройка может быть проще в реализации с точки зрения получения разрешений, финансирования и ввода в эксплуатацию.
- Создание рабочих мест: Промышленная зона может привлечь инвесторов и создать новые рабочие места, что положительно скажется на экономике региона.

Недостатки гипотезы №3:
- Экологические риски: Промышленные предприятия могут негативно влиять на экологическую обстановку в районе, что может вызвать недовольство среди жителей близлежащих жилых зон из-за возможного загрязнения воздуха и шума.
- Ограничения по зонированию: Промышленная застройка может ограничивать возможности для дальнейшего развития жилой зоны, создавая препятствия для расширения социальной инфраструктуры или увеличения зеленых пространств.

### Анализ результатов
В ходе разработки проекта по развитию проектной территории в Сиверском городском поселении была выбрана вторая гипотеза, которая предполагает использование блокированной застройки и индивидуального жилищного строительства (ИЖС) с максимальной высотой зданий до пяти этажей. Выбор данной гипотезы также подтвердился на основе проведения критериальной оценки.

В отличие от первой гипотезы, которая основывалась на высокой жилой застройке (до 9 этажей), вторая гипотеза предлагает более низкие здания, что может лучше соответствовать существующей городской среде и предпочтениям жителей. Блокированная застройка и ИЖС создают более уютные и комфортные условия для проживания, что является важным фактором для повышения качества жизни населения. Вторая гипотеза акцентирует внимание на устойчивом развитии территории, избегая чрезмерной плотности застройки. Это может способствовать созданию более сбалансированной инфраструктуры с учетом потребностей местных жителей, таких как доступ к образовательным и медицинским учреждениям, а также общественному транспорту.
