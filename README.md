# Console menu

## Interactive console menu for C#

*v 1.1.1*

---

### short example code
```csharp
using System;
using Menu;

public class main {
	public static void Main(string[] argv) {

		//create instance with menu header
		ConsoleMenu menu = new ConsoleMenu("Example menu");

		//adding items into menu
		menu.AddItem(new Button("Yes"));    //item index 0
		menu.AddItem(new Button("No"));     //item index 1
		menu.AddItem(new Input("Name"));     //item index 2
		menu.AddItem(new Switcher("Music")); //item index 3

		//method Display() returns index of pressed button and show interactive menu in console
		int menu_id = menu.Display();

		//write id of pressed button
		Console.WriteLine(menu_id);

		//write data of menu item with index 2
		Console.WriteLine((string)menu.GetData()[2]);

		//write data of menu item with index 3
		Console.WriteLine((bool)menu.GetData()[3]);
	}
}
```

---

### Available menu items

* **Button()**
	* closes the menu and returns index of item

* **Switcher()**
	* switches between on and off
	* return data:
		* *bool*

* **Input()**
	* text or number input
	* return data:
		* *string/int*