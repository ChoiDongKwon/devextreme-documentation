Users can scroll the Popup's content. To enable this functionality, wrap the content into the [ScrollView](/concepts/05%20UI%20Components/ScrollView/00%20Overview.md '/Documentation/Guide/UI_Components/ScrollView/Overview/') component and set its **height** and **width** to 100% of the Popup content area:

---
##### jQuery

    <!-- tab: index.js -->
    $(function () {
        $("#popup").dxPopup({
            contentTemplate: () => {
                const content = $("<div />");
                content.dxScrollView({
                    height: "100%",
                    width: "100%"
                });
                return content;
            },
            // ...
        });
    });
 
##### Angular

    <!-- tab: app.component.html -->
    <dx-popup ... >
        <div *dxTemplate="let data of 'content'">
            <dx-scroll-view 
                width="100%"
                height="100%">
                <!-- ... -->
            </dx-scroll-view>
        </div>
    </dx-popup>
    <!-- ... -->

##### Vue

    <!-- tab: App.vue -->
    <template>
        <div id="app-container">
            <DxPopup ... >
                <template #content>
                    <DxScrollView
                        height="100%"
                        width="100%">
                        <!-- ... -->
                    </DxScrollView>
                </template>            
            </DxPopup>
            <!-- ... -->
        </div>
    </template>

    <script>
    // ...
    import { DxScrollView } from "devextreme-vue/scroll-view";

    export default {
        // ...
        components: {
            // ...
            DxScrollView
        }
    }
    </script>


##### React

    <!-- tab: App.js -->
    // ...
    import ScrollView from 'devextreme-react/scroll-view';

        const renderContent = () => {
            return (
                <>
                    <ScrollView height="100%" width="100%">
                        {/* ... */}
                    </ScrollView>
                </>
            )
        };

    const App = () => {
        // ...
        return (
            <div className="App">
                <Popup
                    contentRender={renderContent}
                />
            </div>
        );
    }

    export default App;


---
