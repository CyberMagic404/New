### MVC
В срезе визуальных контролов принимается, что:
* моделью является или [абстрактная модель](https://wasaby.dev/doc/platform/models-collections-types/entity/#wsdataentitymodel) (для простых контролов), или [коллекция](https://wasaby.dev/doc/platform/models-collections-types/icollection/) (для контролов коллекций);
* представлением являются **контролы;**
* контроллерами являются **прикладные модули.**
Схема работы приложения:
* контроллер манипулирует моделью, внося изменения в ее состояние:
    * ___в случае абстрактной модели___ — меняет значения ее полей;
    * ___в случае коллекции___ — добавляет/удаляет/обновляет элементы коллекции;
* представление получает от модели уведомления об изменении состояния и актуализирует внешний вид согласно изменениям.
> [!NOTE] В настоящее время они умеют работать только с одним видом коллекций — [списком записей](https://wasaby.dev/doc/platform/models-collections-types/icollection/#wsdatacollectionrecordset).
##### Диаграмма компонентов для контрола коллекции
![Диаграмма компонентов для контрола коллекции](https://wasaby.dev/materials/resources/doc/images//documentation-platform/ws-data/concept-collection-control-component-diagram.png)
На данной диаграмме представлены:
| Название опции      |Описание          |
| :------------- | :---------------- |
| ***items*** |коллекция, отображаемая контролом;|
| ***dataSource***|источник данных.|
##### Пример
Определим модель пользователя:
```javascript
export default class User extends Model {
	_$format: [
	...
	],
	_$idProperty: 'login',
	authenticate(password) {
		...
	}
}
```
 
