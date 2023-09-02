# flutter_custom_tab_bar_view
//custom_tab_bar_view

import 'package:flutter/material.dart';
import 'package:get/get.dart';

void main() {
  // SystemChrome.setSystemUIOverlayStyle(const SystemUiOverlayStyle(
  //     // systemNavigationBarColor: Colors.blue, // navigation bar color
  //     // statusBarColor: Colors.amber, // status bar color
  //     ));
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return GetMaterialApp(
      debugShowCheckedModeBanner: false,
      theme: ThemeData(),
      home: const HomeScreen(),
    );
  }
}



import 'package:flutter/material.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      length: 3,
      child: Scaffold(
        body: SafeArea(
          child: Column(
            children: [
              const SizedBox(
                height: 10,
              ),
              Center(
                child: Container(
                  height: 60,
                  width: MediaQuery.of(context).size.width * 0.8,
                  decoration: BoxDecoration(
                    borderRadius: BorderRadius.circular(30.0),
                    color: Colors.amber,
                  ),
                  child: Padding(
                    padding: const EdgeInsets.all(8.0),
                    child: TabBar(
                      indicatorColor: Colors.amber,
                      indicator: BoxDecoration(
                        color: Colors.green[500],
                        borderRadius: BorderRadius.circular(30.0),
                      ),
                      labelColor: Colors.black,
                      unselectedLabelColor: Colors.blue,
                      tabs: const [
                        Tab(
                          text: "Page 1",
                        ),
                        Tab(text: "Page 2"),
                        Tab(text: "Page 3"),
                      ],
                    ),
                  ),
                ),
              ),
              Expanded(
                child: TabBarView(
                  children: [
                    Container(
                      width: double.maxFinite,
                      height: double.maxFinite,
                      color: Colors.grey,
                      child: const Center(child: Text("page 1")),
                    ),
                    const Text("Page 2"),
                    const Text("Page 3"),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
