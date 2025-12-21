Шаг 1. Проверка запуска minikube:
<img width="1512" height="544" alt="Снимок экрана 2025-12-20 в 18 09 50" src="https://github.com/user-attachments/assets/00b8dca7-ae5e-4269-a9de-811e593472aa" />

Шаг 2. Создаем объекты в кластере:

<img width="1512" height="107" alt="Снимок экрана 2025-12-20 в 18 19 15" src="https://github.com/user-attachments/assets/eeb15a20-cc36-4a2a-bed8-843b00e00a07" />

Вопрос: важен ли порядок выполнения этих манифестов?
Почему?

Да.

Service и Deployment ссылается на поды app в selector. В свою очередь Deployment ссылается на configmap в configMapRef.


Шаг 3. Проверить, что все ресурсы успешно создались, с помощью команды

<img width="594" height="178" alt="Снимок экрана 2025-12-20 в 18 39 42" src="https://github.com/user-attachments/assets/73bbefce-b2b5-4da2-90b3-19661cf949ea" />


Шаг 4. Создать nextcloud.yml и повторить для него шаги 1-3

<img width="675" height="431" alt="Снимок экрана 2025-12-20 в 19 15 51" src="https://github.com/user-attachments/assets/2d755579-0c36-449d-bd69-526055ef6357" />

Шаг 5. Проверка состояния пода.

<img width="1237" height="327" alt="Снимок экрана 2025-12-21 в 17 07 23" src="https://github.com/user-attachments/assets/6a2cfa54-318d-428f-a83e-099fd4ce5fa8" />

Часть 3. Шаг 1.

Зададим порт для перенаправления запроса извне

<img width="820" height="323" alt="Снимок экрана 2025-12-21 в 17 16 25" src="https://github.com/user-attachments/assets/113dc900-0731-49d7-8a5a-6e970536d705" />

Шаг 2. Осуществим туннелирование между нодой minikube и локалхостом

<img width="779" height="223" alt="Снимок экрана 2025-12-21 в 17 44 46" src="https://github.com/user-attachments/assets/e474a6bf-7861-4ec5-a661-d4a1a5dd5441" />

<img width="1512" height="982" alt="Снимок экрана 2025-12-21 в 17 44 28" src="https://github.com/user-attachments/assets/0a89779a-e4f7-4d4e-9f96-72d4817ccea8" />

Шаг 3. Дашборд для minikube

<img width="871" height="196" alt="Снимок экрана 2025-12-21 в 17 48 16" src="https://github.com/user-attachments/assets/a07532af-7fe2-46af-833e-4065f32442b5" />

<img width="1512" height="982" alt="Снимок экрана 2025-12-21 в 17 48 02" src="https://github.com/user-attachments/assets/c1c25132-d778-43f3-b81d-e336a6add979" />

Вопрос: что (и почему) произойдет, если отскейлить
количество реплик postgres-deployment в 0, затем обратно в 1,
после чего попробовать снова зайти на Nextcloud?

В deployment работает персистентностть данных. При реплика=0 postgres под будет удален и nextcloud не должен будет работать, однако данные буду сохранены. При реплика=1 postgres под снова поднимется со старыми сохраненными данными 


