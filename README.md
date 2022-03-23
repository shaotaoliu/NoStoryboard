# NoStoryboard

This app shows how to create an iOS app without using storyboards.

From AppDelegate:
```Swift
        window = UIWindow(frame: UIScreen.main.bounds)
        window?.makeKeyAndVisible()
        window?.backgroundColor = .systemBackground
        window?.rootViewController = ViewController()
```

From SceneDelegate:
```Swift
        guard let windowScene = (scene as? UIWindowScene) else { return }
        
        let window = UIWindow(frame: windowScene.coordinateSpace.bounds)
        window.windowScene = windowScene
        self.window = window
        
        let navigationController = UINavigationController()
        window.rootViewController = navigationController
        window.makeKeyAndVisible()
        
        let controller = ViewController()
        navigationController.pushViewController(controller, animated: false)
```
