# Коэффициент восстановления золота из золотосодержащей руды

## Описание задачи
Построить модель, которая на основании данных с параметрами добычи и очистки поможет оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками.

## Данные

В распоряжении сырые данные с параметрами добычи и очистки.

gold_recovery_train.csv — обучающая выборка;  
gold_recovery_test.csv — тестовая выборка;  
gold_recovery_full.csv — исходные данные.  

Данные индексируются датой и временем получения информации (признак date). Соседние по времени параметры часто похожи.  
Некоторые параметры недоступны, потому что замеряются и/или рассчитываются значительно позже. Из-за этого в тестовой выборке отсутствуют некоторые признаки, которые могут быть в обучающей. Также в тестовом наборе нет целевых признаков.

## Примечание

Модель не прошла sanity-check, т.к показала значение метрики качества хуже, чем константная модель.
Необходимо доработать модель.  
Варианты улучшения: 
1. Разобраться с выбросами (применить разные принципы и пороги обнаружения выбросов по признакам)
2. Поробовать использовать различные принципы замены пустых значения, например, KImputer, т.к у нас есть информация о том, что соседние параметры похожи
3. Определить самые важные признаки, исключить наименее важные и пересчитать метрики (Для определения признаков можно попробовать Lasso linear model, feature_importance?, eli5?)
4.  
