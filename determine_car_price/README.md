# Определение стоимости автомобилей  
## Описание проекта    

Сервис по продаже автомобилей с пробегом «Не бит, не крашен» разрабатывает приложение для привлечения новых клиентов. В нём можно быстро узнать рыночную стоимость своего автомобиля. В вашем распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей. Вам нужно построить модель для определения стоимости.   

Заказчику важны:  
- качество предсказания;
- скорость предсказания;
- время обучения.

Провести исследование 3-х моделей машинного обучения: RandomForest, CatBoost, LightGBM, XGBoost.  

Использовать в качестве метрики качества - RMSE.  

## Данные 

- `DateCrawled` — дата скачивания анкеты из базы  
- `VehicleType` — тип автомобильного кузова  
- `RegistrationYear` — год регистрации автомобиля  
- `Gearbox` — тип коробки передач  
- `Power` — мощность (л. с.)  
- `Model` — модель автомобиля  
- `Kilometer` — пробег (км)  
- `RegistrationMonth` — месяц регистрации автомобиля  
- `FuelType` — тип топлива  
- `Brand` — марка автомобиля  
- `NotRepaired` — была машина в ремонте или нет  
- `DateCreated` — дата создания анкеты  
- `NumberOfPictures` — количество фотографий автомобиля  
- `PostalCode` — почтовый индекс владельца анкеты (пользователя)  
- `LastSeen` — дата последней активности пользователя  
Целевой признак
- `Price` — цена (евро)  

# ВЫВОДЫ:  

1. Выполнили очистку и предобработку данных  
2. Обучили несколько моделей: LinearRegression, DecisionTree, RandomForest, LightGBM, Catboost, XGBoost  
3. Осуществили поиск лучших гиперпараметров для модели при помощи RandomizedSearchCV    
4. Для каждой модели замерялось время обучения и предсказания  
5. По итогам замеров определили, что наилучшие параметры(время обучения, время предсказания, метрика качества RMSE) получила модель LightGBM  


| model         | wall_time_fit      | wall_time_predict | rmse  |
| ------------- |:------------------:| -----------------:|------:|
| LinearRegression     | 0.89    | 0.01 | 2895.437373
| DecisionTree    | 59.54 |   0.07 | 1865.041631
| RandomForest  | 60.25         |    0.81 | 1685.669598
| LightGBM  | 1.47         |    0.64 | 1600.339198
| Catboost  | 71.54         |    0.15 | 1630.081602
| XGBoost  | 29.03         |    0.26 | 1613.273064
