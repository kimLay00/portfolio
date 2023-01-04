<template>
    <v-container grid-list-xl>
      <h2 class="pl-4">
        <span>Project</span>
        <span class="light-blue--text text--darken-1">Experience</span>
      </h2>
      <v-layout row justify-center align-center wrap class="mt-4 pt-2">
        <v-dialog
          v-model="project.dialog"
          lazy
          max-width="600"
          v-for="project in projects"
          :key="project.title"
        >
          <template v-slot:activator="{ on }">
            <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
              <v-card hover flat color="transparent">
                <v-img
                  :src="project.keyImage"
                  :alt="project.title"
                  height="230"
                  lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
                ></v-img>
                <v-card-title primary-title class="justify-center">{{project.title}}</v-card-title>
              </v-card>
            </v-flex>
          </template>
          <v-card v-if="project.dialog">
            <v-card-title class="text-h1">
                <h1 class="headline mb-0 font-weight-bold light-blue--text text--darken-1">
                    <span>{{project.title}}</span>
                </h1>
            </v-card-title>
            <v-card-text>
              <h2 class="mb-0">
                <span>Description</span>
              </h2>
              <div v-for="($descripton, $index) in project.description"
                :key="`description${$index}`"
                class="projectDescriptionContainer"
              >
                <v-img 
                contain
                :src="$descripton.image"
                width="100%"
                >
                </v-img>
                <span>{{$descripton.text}}</span>
              </div>
              <h2 class="mb-0">
                <span>Technology</span>
              </h2>
              <v-chip v-for="($tech, $index) in project.tech" 
                :key="`techChip${$index}`"
                color="light-blue" text-color="white"
              >
                {{ $tech }}
              </v-chip>
            </v-card-text>
          </v-card>
        </v-dialog>
      </v-layout>
    </v-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        dialog: false,
        projects: [
          {
                dialog: false,
                title: "Card Game",
                keyImage: require('../assets/cardGame/cardGameImage.jpeg'),
                tech: ["Vue", "Typescript", "SCSS", "Javascript", "MVC"],
                description: [
                {
                    image: require('../assets/cardGame/cardGameImage.jpeg'),
                    text: "Desktop and Mobile card games are developed in MVC structure.\n New games, features and bug fix are made on this project.\n Reusable and easy maintainable code are pursued in this project. This experience encourages me to keep a good coding practice."
                },
                
                ]
            },
        {
                dialog: false,
                title: "Prize Drawing Site",
                keyImage: require('../assets/prizeDrawing/luckyDraw.png'),
                tech: ["Javascript", "HTML", "CSS", "MVC"],
                description: [
                {
                    image: require('../assets/prizeDrawing/luckyDraw.png'),
                    text: "Prize Drawing logic is designed and developed by me. Instant function is called by controller for deciding what prize is drawn and will display on view."
                },
                
                ]
            },          
          {
                dialog: false,
                title: "Whitelabel CMS",
                keyImage: require('../assets/whitelabelCMS/keySettings.jpg'),
                tech: ["Angular", "Node.js", "Express.js", "CSS"],
                description: [
                  {
                      image: require('../assets/whitelabelCMS/keySettings.jpg'),
                      text: "Key Settings page provide a list of whitelabel keys for user to edit."
                  },
                  {
                      image: require('../assets/whitelabelCMS/keySettingContent.jpg'),
                      text: "Corresponding whitelabel key content of all whitelabel will be displayed after clicking edit. 1 of the whitelabel can be edit as model value and can apply same value to other whitelabels by selection of 'Copy Value As Model Value'."
                  },
                  {
                      image: require('../assets/whitelabelCMS/exportCommitToGit.jpg'),
                      text: "'Export' or 'Commit and Push to GIT' can be clicked after modification of whitelabel key value. Export triggers download of whitelabel zip folder, it provides a quick whitelabel files preview for users after edit. "
                  },
                  {
                      image: require('../assets/whitelabelCMS/commitMessage.jpg'),
                      text: "'Commit and Push to GIT' allows users to push the changes to git repository. "
                  },
                  {
                      image: require('../assets/whitelabelCMS/bannerConfig.jpg'),
                      text: "Banner Config page allows user to edit banner content of whitelabels. This page enables modification of banner order and upload of new banner in different languages."
                  },
                  {
                      image: require('../assets/whitelabelCMS/crazyBannerConfig.jpg'),
                      text: "Crazy Banner is a video to be displayed after game login. This page allows preview of current crazy banner and support upload of video. User can set whether crazy banner is displayed on corresponding whitelabel and edit crazy banner content."
                  },
                ]
            },
            {
                dialog: false,
                title: "Translate Tools",
                keyImage: require('../assets/translateTools/insertKeyWords.jpg'),
                tech: ["Angular", "Node.js", "MongoDB", "Express.js", "CSS"],
                description: [
                  {
                      image: require('../assets/translateTools/insertKeyWords.jpg'),
                      text: "Insert Keyword in search box and with selection of input language"
                  },
                  {
                      image: require('../assets/translateTools/selectOutputLang.jpg'),
                      text: "Output translate language can be selected from box aside."
                  },
                  {
                      image: require('../assets/translateTools/filterResult.jpg'),
                      text: "User can further filter search result in order to retrieve target translation quickly."
                  },
                ]
            },
          {
                dialog: false,
                title: "Integration Center",
                keyImage: require('../assets/integrationCenter/Homepage.png'),
                tech: ["Javascript", "jQuery", "HTML", "CSS"],
                description: [
                {
                    image: require('../assets/integrationCenter/Homepage.png'),
                    text: "Integration Center provides platform for agents to manage accounts by themselves. They usually raise their request to CS team for managing their request manually. The introduction of this page allows agents to read their request status clearly and have a better understanding of their account information."
                },
                {
                    image: require('../assets/integrationCenter/Login.png'),
                    text: "Login is needed for agents to read their account's info."
                },
                {
                  image: require('../assets/integrationCenter/WorkOrder.png'),
                  text: "User can check work order list for raised request's details. Sortings and data filtering is enabled, user can search related requests by date, title, work order code and request status."
                },
                {
                  image: require('../assets/integrationCenter/WorkOrderDetails.png'),
                  text: "Work Order details provide request details for user to read. They can leave comments or edit request on this page."
                },
                {
                  image: require('../assets/integrationCenter/CreateWorkOrder.png'),
                  text: "Work Order can be created on this page. Validation rules are implemented to prevent user inputting incorrect information."
                },
                {
                  image: require('../assets/integrationCenter/UserInfo.png'),
                  text: "User Info page enables user to read their account details. They can edit account info, e.g. password reset, on this page as well."
                },
                {
                  image: require('../assets/integrationCenter/NotificationCenter.png'),
                  text: "Notification will be sent to user when there's update on work orders. User can check notifications on this page."
                }
                ]
            },
            {
                dialog: false,
                title: "Metlife Discovery",
                keyImage: require('../assets/metlifeDiscovery/dataFillingPage.png'),
                tech: ["HTML", "JavaScript", "JQuery", "CSS", "NodeJS", "MSSQL"],
                description: [
                  {
                    image: require('../assets/metlifeDiscovery/dataFillingPage.png'),
                    text: "Fill in user's basic information, e.g. age, gender, occupation etc."
                  },
                  {
                    image: require('../assets/metlifeDiscovery/productSuggestion.jpeg'),
                    text: "Suggested insurance product will be recommended according to information provided by user."
                  },
                  {
                    image: require('../assets/metlifeDiscovery/recommendedProduct.png'),
                    text: "User can click product bar for reading product details."
                  },
                ]
              },
              {
                    dialog: false,
                    title: "Metlife Corporate Site",
                    keyImage: require('../assets/metLifeCorporateSite/corporateSiteScreenCapture.jpeg'),
                    tech: ["Javascript", "HTML", "Adobe Experience Manager"],
                    description: [
                    {
                        image: require('../assets/metLifeCorporateSite/corporateSiteScreenCapture.jpeg'),
                        text: "Site Update and maintenance is made on this project."
                    },
                    
                    ]
                },
        ]
      };
    }
  };
  </script>
  
  <style  scoped>
    .projectDescriptionContainer{
        margin-bottom: 10px;
    }
  </style>