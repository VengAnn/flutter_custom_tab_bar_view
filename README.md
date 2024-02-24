# flutter_custom_tab_bar_view
//custom_tab_bar_view

class MainPage extends StatelessWidget {
  const MainPage({super.key});

  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      length: 3,
      child: Scaffold(
        body: SafeArea(
          child: Column(
            children: [
              SizedBox(
                height: Dimensions.height20,
              ),
              Container(
                height: 40,
                width: MediaQuery.of(context).size.width * 0.8,
                decoration: BoxDecoration(
                  borderRadius: BorderRadius.circular(30.0),
                  color: Colors.amber,
                ),
                child: TabBar(
                  dividerColor: Colors.transparent, // hide divider
                  indicatorColor: Colors.amber,
                  //indicatorSize this show tab fill when click
                  indicatorSize: TabBarIndicatorSize.tab,
                  indicator: BoxDecoration(
                    color: Colors.green[500],
                    borderRadius: BorderRadius.circular(30.0),
                  ),
                  labelColor: Colors.black,
                  unselectedLabelColor: Colors.blue,
                  tabs: const [
                    Tab(
                      text: "Home",
                    ),
                    Tab(text: "Page 2"),
                    Tab(text: "Page 3"),
                  ],
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
