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

