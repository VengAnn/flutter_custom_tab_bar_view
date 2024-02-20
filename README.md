# flutter_custom_tab_bar_view
//custom_tab_bar_view
// this custom tap bar
class StackOver extends StatefulWidget {
  @override
  _StackOverState createState() => _StackOverState();
}

class _StackOverState extends State<StackOver>
    with SingleTickerProviderStateMixin {
  late TabController _tabController;

  @override
  void initState() {
    super.initState();
    _tabController = TabController(length: 2, vsync: this);
  }

  @override
  void dispose() {
    _tabController.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Tab bar'),
      ),
      body: Padding(
        padding: const EdgeInsets.all(8.0),
        child: Column(
          children: [
            _buildTabBar(),
            Expanded(
              child: TabBarView(
                controller: _tabController,
                children: [
                  _buildTabBarView("Place Bid"),
                  _buildTabBarView("Buy Now"),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }

  Widget _buildTabBar() {
    return Container(
      width: 300,
      height: 45,
      decoration: BoxDecoration(
        color: Colors.grey, // Set the green color here
        borderRadius: BorderRadius.circular(25.0),
      ),
      child: TabBar(
        dividerColor: Colors.white,
        controller: _tabController,
        tabAlignment: TabAlignment.fill,
        indicator: BoxDecoration(
          borderRadius: BorderRadius.circular(25.0),
          color: Colors.yellow.withOpacity(0.5), // Adjust opacity if necessary
        ),
        indicatorSize:
            TabBarIndicatorSize.tab, // this  set to fill container on tap
        labelColor: Colors.white,
        unselectedLabelColor: Colors.black,
        tabs: [
          Tab(
            child: Row(
              children: [
                Expanded(
                  child: Container(
                    decoration: BoxDecoration(
                      borderRadius: BorderRadius.circular(10),
                      // color: const Color.fromARGB(255, 2, 28, 2),
                    ),
                    child: const Center(child: Text("Place Bid")),
                  ),
                )
              ],
            ),
          ),
          Expanded(
            child: Tab(
              child: Row(
                children: [
                  Expanded(
                    child: Container(
                      width: double.infinity,
                      decoration: BoxDecoration(
                        borderRadius: BorderRadius.circular(10),
                        //color: Color.fromARGB(255, 20, 218, 20),
                      ),
                      child: const Center(
                        child: Text(
                          "buy now",
                        ),
                      ),
                    ),
                  )
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }

  Widget _buildTabBarView(String text) {
    return Center(
      child: Text(
        text,
        style: TextStyle(
          fontSize: 25,
          fontWeight: FontWeight.w600,
        ),
      ),
    );
  }
}

