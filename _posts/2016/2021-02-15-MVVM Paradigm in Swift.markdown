

---
title: The MVVM Paradigm
subtitle: It's use in Swift
---



This is a brief post on how MVVM can be implemented in a new project,be it an app or a website, MVVM is a way you can separate your Business Logic from your Data.
Before I get into more details about how it is implemented in SwifUI, I will try to explain the basics of this pattern.

What is **MVVM**?

- MVVM is a design architecture pattern in software development.


What is a **Design Pattern**?

- A design pattern or an architecture pattern is a re-usable form of a solution to a design problem.


Is MVVM the only design pattern of sorts to use in application development?

- No, there are many other patterns in software development.

**Examples:**

1. **HMVC** - Hierarchical Model-View-Controller.
2. **MVP** - Model View Presenter.
3. **MVA** - Model View Adapter.
4. **PAC** - Presentation Abstraction Control.
5. **RMR** - Resource-Method-Representation.
6. **ADR** - Action-Domain-Responder.



**MVVM** Definition -

- The **Model-View-ViewModel** **(MVVM) ** helps to cleanly separate the business and presentation logic of an application from its user interface (UI).

Maintaining a clean separation between application logic and the UI helps to address numerous development issues and can make an application easier to test, maintain, and evolve. It can also greatly improve code re-use opportunities and allows developers and UI designers to more easily collaborate when developing their respective parts of an app.



*** MVVM Pattern Components***

MVVM is a triad, which means it has **3** core components : 

- The **Model**, 

- The **View**, and 

- The **ViewModel**. 

Each component serves a distinct purpose. 



**The Model** – A Model represents the data in your application.The Model has a set of structs or classes that encapsulates the business logic and data in the application.

Data can be from a data source, 

The datasource can be a 

- remote URL. 
- local files.  
- XML format from remote URL. 
- data stored in a JSON file in a Bundle. 
- from a BAAS ( Backend as a Service)
- data stored in CoreData database etc.

A Model must be kept as simple as to reflect/represent the data structure of the data source. Model (Backend) is always UI-independent. 

> The MODEL is the source of truth for that app.

Example of a **Model** in **SwiftUI**.

```
import SwiftUI
// MARK: - WoodWorks MODEL

struct WoodWorks: Identifiable, Codable, Equatable {
    var id = UUID()
    var title: String
    var comments: String
    var image: String
    var rating: Int
    var noOfPastOrders: Int
    var totalVisits: Int
    var overview: [String]
    var product: [String]
    var isEditorChoice: Bool
    var isTrending: Bool
}
``` 

**The View** –  It is the UI i.e. the front end of the application. 

A **View** reflects the data in the **Model**. Data moves from a Model to the VIEW.
Views are reactive in SwiftUI i.e when the Model changes/modified the UI reacts to that Model and updates the Views, how this happens will be discussed in detail in the ViewModel section.


In an MVVM paradigm, View is stateless and dependent on ViewModel to provide it with different View states. The view is passive/stateless, which means

- The view does not pull data from the view model.
- The view is not responsible for updating itself from the view model.
- The view has its state managed by the view model.


![ViewState.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1613448702241/iynyA8Xs2.jpeg)


A View subscribes to a ViewModel, which means it is declarative and whenever there is a change in the Model the ViewModel publishes those changes across the app. The View based on the new data will display the new/modified data to the user.


The View presents the user with UI elements such as buttons, Text Fields, add menu/details and search area etc.When a user tries to interact with the app,it is called an Intent. Your intents are handled by the **ViewModel**.

Example of a **VIEW** in **SwiftUI**

```
import SwiftUI

struct Experiment: View {
    var woodWorks: WoodWorks
    @State private var showAlertAddFavorite: Bool = false
    @EnvironmentObject var favoriteViewModel: FavoriteViewModel
    @EnvironmentObject var furnitureViewModel: FurnitureViewModel
    var body: some View {
        ScrollView(.vertical, showsIndicators: false) {
            VStack (alignment: .center, spacing: 0) {
                // IMAGE
                ZStack(alignment: .bottom) {
                    ImageLoaderView(imageUrl: woodWorks.image)
                        .scaledToFit()
                    HStack {
                        Spacer()
                        Button(action: {
                            if self.furnitureViewModel.favorite {
                                self.favoriteViewModel.removeProductFromFavorites(woodWorks: self.woodWorks)
                                self.furnitureViewModel.setFavorite(flag: false)
                            } else {
                                self.favoriteViewModel.addProductToFavorites(woodWorks: self.woodWorks)
                                self.furnitureViewModel.setFavorite(flag: true)
                                self.showAlertAddFavorite.toggle()
                                DispatchQueue.main.asyncAfter(deadline: .now() + 1.0) {
                                    self.showAlertAddFavorite.toggle()
                                }
                            }
                        }) {
                            Image(systemName: furnitureViewModel.favorite ? "bookmark.fill" : "bookmark")
                                .font(.system(size:30, weight: .light))
                                .foregroundColor(Color.white)
                                .shadow(color: Color.gray, radius: 2, x: 0, y: 0)
                                .padding(20)
                        }
                    }
                    }
            }
        }
        .edgesIgnoringSafeArea(.top)
    }
}
struct Experiment_Previews: PreviewProvider {
    static var previews: some View {
        Experiment(woodWorks: sampleWorks[0])
            .environmentObject(FavoriteViewModel())
            .environmentObject(ShoppingListViewModel())
            .environmentObject(FurnitureViewModel(woodWorks: sampleWorks[0]))
    }
}
``` 
The view looks like this. When the User clicks on Favorites systemimage(systemName **bookmark.fill**), it is added to the favorites list. 


![ProductView.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1613505881390/v3aeJuDuP.jpeg)

If the user clicks on the Favorites tab he can view the added product.


![Favorite Tab.JPEG](https://cdn.hashnode.com/res/hashnode/image/upload/v1613505894075/VZo8ccW3S.jpeg)


 **The ViewModel** – A ViewModel acts as an intermediary between the View and the Model. The viewmodel, which interprets the Model for the Views, easily manages and presents data objects. A ViewModel is used by the View for displaying the data objects and different View states.

A ViewModel is typically declared as a **Class** in SwifUI. A Class in SwiftUI is a reference type, not a value type. Classes are stored in heap memory and any View in your app can access that reference pointer and interact with the ViewModel.

User Interactions i.e all the Intent functions are defined in a ViewModel.The ViewModel changes the Model based on User inputs. ViewModel contains business logic for preparing the data from the Model in the form required by the View. This logic/function can append, delete or modify the data.

A ViewModel never interacts with a View but it merely announces/publishes the changes in the Model. It binds the “View” to a “Model” and sends the changes to Views when the Model is changed. A ViewModel can also update a Model when needed.

Example of a **ViewModel** in **SwiftUI**

```
import SwiftUI
// MARK: - WoodWorks DATA

final class FavoriteViewModel: ObservableObject {
    @Published var favoriteWoodWorks: [WoodWorks] = []
    let defaults = UserDefaults.standard
    init() {
        let data = defaults.data(forKey: keyFavorites)
        if (data != nil) {
            favoriteWoodWorks = try! JSONDecoder().decode([WoodWorks].self, from: data!)
        }
    }
}
extension FavoriteViewModel {
    func addProductToFavorites(woodWorks: WoodWorks) {
        favoriteWoodWorks.append(woodWorks)
        let data = try! JSONEncoder().encode(favoriteWoodWorks)
        defaults.set(data, forKey: keyFavorites)
    }
    func removeProductFromFavorites(woodWorks: WoodWorks) {
        if let index = favoriteWoodWorks.firstIndex(of: woodWorks) {
            favoriteWoodWorks.remove(at: index)
        }
        let data = try! JSONEncoder().encode(favoriteWoodWorks)
        defaults.set(data, forKey: keyFavorites)
    }
}
``` 
As you can see **FavoriteViewModel** is a **CLASS**. This particular ViewModel adds and removes a Product object woodWorks of type WoodWorks model as a Favorite product based on the user interaction with the app. 
This class has a **@Published** var **favoriteWoodWorks** which is an array of **WoodWorks** struct, the model in the application.

The **addProductToFavorites** is an Intent function,which is called in Product **View**. When the user clicks **Favorite** **systemimage** button, this function is called and defaults database saves the new product to the **favoriteWoodWorks** object.

**defaults.set** method has two arguments to pass

1. Object  : The object to store in the defaults database.

2. defaultName : The key with which to associate the object.

Similarly intent function **removeProductFromFavorites** removes a woodWorks object from favoriteWoodWorks object when unselected from the View. The function then calls defaults.set method to save the updated products from favoriteWoodWorks object.

The ViewModel class in SwiftUI conforms to **ObservableObject** protocol. Classes that conform to the ObservableObject protocol can use SwiftUI’s **@Published** property wrapper to automatically announce changes to properties. Any **views** using the object get their **body** property re-invoked and stay in sync with the data.

![0EF69BD7-A2BC-44A9-A8AF-D83B6C3B5711.JPEG](https://cdn.hashnode.com/res/hashnode/image/upload/v1613446106784/4B8MrSVyv.jpeg)

The observableobject publishes the changes to the world whenever there is a change in the Model or data in the application. The View simply observes/subscribes to the Model changes and displays the new data. The ViewModel changes the Model based on User inputs in the application Views. 

This is how a **ViewModel** facilitates the flow of data from the **Model** to the **View** and updates the Model when a user interacts with the View and performs an intent.



# **Benefits of using MVVM**


- Speed and performance enhancements.
- Faster screen saving/loading.
- Collaborative working.
- Code Reuse.
- Ease of testing.
- Data Bindings make UI updates easier to handle.
- Ease of maintainability.
- No inter-view dependencies: Since we only have view-specific states, unforeseen inter-view state dependencies are not possible.




# **Drawbacks of using MVVM**


- MVVM can be an "overkill" for simple UI operations. 
- For larger applications, generalizing the ViewModel becomes more difficult.
- There is considerable memory consumption with data binding in very large applications.
- No single source of truth: Since different ViewModels are rather separate objects and do not necessarily share a state, there is no single source of truth by default.
****
