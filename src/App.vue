<template>
    <root>
        <app-navigation></app-navigation>
    </root>
</template>

<script>
import { createAppContainer, createStackNavigator, createDrawerNavigator } from "vue-native-router";
import { Root } from "native-base";

import HomeScreen from "./screens/home/Index.vue";
import DetailScreen from "./screens/detail/Index.vue";

const DrawerNavigator = createDrawerNavigator(
    {
        Home: { screen: HomeScreen },
        Detail: { screen: DetailScreen },
    },
    {
        initialRouteName: "Home",
        /*contentOptions: {
            activeTintColor: "#e91e63"
        },*/
        //contentComponent: SideBarScreen
    }
);

const StackNavigator = createStackNavigator(
    {
        //Drawer: { screen: DrawerNavigator },
        Home: { screen: HomeScreen },
        Detail: { screen: DetailScreen },
    },
    {
        initialRouteName: "Home",
        headerMode: "none"
    }
)

const AppNavigation = createAppContainer(StackNavigator);

export default {
    components: { Root, AppNavigation }
}
</script>
