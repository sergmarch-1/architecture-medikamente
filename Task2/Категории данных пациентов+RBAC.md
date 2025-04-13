Категория данных	|   Описание    |	Домен   |

PII                 |	ФИО, дата рождения, паспорт, СНИЛС           |	person.identity
Contact             |	Телефон, email, адрес                        |	person.contact
Medical             |	Результат осмотра, диагноз, направления      |	health.clinical
LabResults          |	Результаты анализов                          |	health.lab
Payment             |	Сумма, дата, услуга, номер кассы             |	finance.payment
Consent             |	Согласие на обработку, отозванное согласие   |	legal.consent



Роль            |	Доступ к доменам

PATIENT         |	Только к своим данным: identity, contact, health.lab, visit, payment
RECEPTIONIST    |	person.identity, person.contact, legal.consent
DOCTOR          |	health.clinical, health.lab, person.identity, только для своих пациентов
CASHIER         |	finance.payment, только текущие операции
ANALYTIC        |	анонимизированные данные из всех доменов (INT), кроме person.identity 
ADMIN           |	доступ ко всем данным по умолчанию, кроме PII и MED (требуется доп.разрешение через DLP)