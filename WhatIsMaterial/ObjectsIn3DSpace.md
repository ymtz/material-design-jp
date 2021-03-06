Objects in 3D space
===

There are parallels between organizing objects in the physical world and arranging objects in space in material design. In the physical world, objects can be stacked or affixed to one another, but cannot pass through one another. The objects cast shadows and reflect light.

物理的な世界内のオブジェクトを整理し、マテリアル設計のスペース内のオブジェクトを配置することとの間に類似点があります。物理的な世界では、オブジェクトは、積み重ねることができ、又は互いに固定されたが、互いを通過することができない。オブジェクトには影をキャストして光を反射する。

These qualities apply to objects in material design and help create a spatial model that can be consistently applied across apps in ways that are familiar to users.

これらの資質は、マテリアル設計内のオブジェクトに適用され、一貫して、ユーザーによく知られている方法でのアプリの間に印加することが可能な空間モデルを作成するのに役立つ。

### Elevation

#### Elevation

Elevation is the relative position of an object along its parent’s z-axis. Elevation is the relative value between parent and child objects.

標高は親のz軸に沿って物体の相対的な位置である。標高は、親と子オブジェクト間の相対的な値です。

Elevation is measured in the same units as the x and y axes, typically in density independent pixels (dps). Since material has a standard 1dp thickness, all elevation distances are measured from one top surface to another top surface.

仰角は、典型的には、密度の独立した画素（dps）で、x軸およびy軸と同じ単位で測定される。マテリアルは、標準的な1dp厚さを有しているので、すべての昇降距離は、別の上面一つの上面から測定される。

#### Resting elevation

All material objects have a resting elevation, whether the object is a small component or a sheet that spans the entire display.

すべてのマテリアルのオブジェクトは、オブジェクトが、小さな部品やディスプレイ全体にまたがるシートであるかどうか、休んで標高を持っています。

In the static state, the resting elevation for an object does not change. It is constant throughout an app. If an object changes elevation, it should return to its resting elevation as soon as possible.

静的な状態では、オブジェクトのための休息上昇は変更されません。それはアプリを通して一定である。オブジェクトは標高を変更した場合、それはできるだけ早くその静止標高に返す必要があります。

The resting elevation for a given component type is consistent across apps throughout a platform. However, that same component type may have different resting elevations from platform to platform depending on the depth of the environment (e.g., TV has a greater depth than mobile or desktop).

指定されたコンポーネントタイプの休憩標高は、プラットフォーム全体でのアプリ間で一貫している。しかし、その同じコンポーネントタイプは、環境（例えば、テレビ、モバイルやデスクトップよりも大きな深さを有する）の深さに応じて、プラットフォームとは異なる静止上昇を持っている場合があります。

#### Responsive elevation and dynamic elevation offsets

Certain component types have responsive elevation, which means they change their elevation in response to user input or system events. Different component states (e.g., normal, focused, pressed) may result in varying elevation changes, which are consistently implemented using dynamic elevation offsets.

特定のコンポーネントタイプは、それらがユーザーの入力またはシステムイベントに応答してその高さを変更することを意味し、応答性の上昇を持っている。異なるコンポーネントの状態（例えば、正常な、集中し、押され）常に動的標高オフセットを使用して実装される高度の変化を、変化させることをもたらし得る。

Dynamic elevation offsets are relative to the resting state of the component, and act as the goal or target elevation for the component to move towards for a given component state. They also ensure that elevation changes for a given action are consistent across a component type. For example, all components that lift on press have the same elevation change, relative to their current/resting elevation.

ダイナミック標高オフセットは、コンポーネントが指定されたコンポーネントの状態のために向かって移動するための目標や目標標高などの静止コンポーネントの状態、および行為に対するものである。彼らはまた、特定のアクションのために、その標高変化はコンポーネントタイプ全体で一貫していることを確認してください。例えば、プレスで持ち上げて、すべてのコンポーネントは、現在/休息標高に対する相対同じ標高変化を持っている。

Once the input event is completed or cancelled, the component will return to its resting elevation.

入力イベントが完了するかまたは取り消されると、コンポーネントはその静止標高に戻ります。

#### Functional shadows

Shadows provide several important visual cues about the arrangement of objects in space. Shadows are the only visual affordance indicating the amount of separation between surfaces. The elevation of an object determines the visual appearance of its shadow.

影は、空間内のオブジェクトの配置に関するいくつかの重要な視覚的な印象を与えます。影が表面間の距離を示す唯一の視覚的な影響です。オブジェクトの上昇はその影の外観を決定します。

Without a shadow, there is nothing to indicate that the floating action button is a separate surface from the background surfaces.

影なしで、浮いているアクションボタンは、背景表面から独立した表面であることを示すものは何もないです。

Crisp shadows indicate both the floating action button and the app bar are separate surfaces very close to the background surface.

クリスプシャドウが浮いているアクションボタンと、アプリバーの両方がバックグラウンド表面に非常に近い独立した表面であることを示します。

Softer, larger shadows indicate the floating action button is at a higher elevation than the app bar.

柔らかく大きな影が浮いているアクションボタンは、アプリバーよりも高い位置にあることを示します。

In motion, shadows also provide cues about an object’s direction of movement. This is another useful tool to indicate whether the distance between surfaces is increasing or decreasing.

「動き」では、影も動きのオブジェクトの方向についての手がかりを提供します。これは表面の間の距離が増加または減少しているかどうかを示すためにの別の有用なツールです。

Without a shadow to indicate elevation, it’s unclear whether this circle is scaling at the same elevation, or simply increasing its elevation.

影が上昇を指示することなく、この円が同じ高さにスケーリング、または単にその高さを増加しているかどうかは不明です。

The shadow grows softer and larger as the object’s elevation increases and grows crisper and smaller as the elevation decreases.

影は、オブジェクトの標高が高いほど柔らかく、大きくなると仰角が小さくなるにつれてはっきりと小さい成長する。

In this case, the consistent shadow helps the user understand that the object is changing shape as opposed to changing elevation.

この場合には、一貫性の影は、ユーザが高さを変えることとは対照的に、物体の形状を変えていることを理解するのに役立ちます。


### Object relationships

How you organize objects in an app determines how objects or collections of objects move in relation to one another. Objects can move independently of each other, or their movement can be constrained to, and dependent upon, their container. Containers and the objects they contain have a parent-child relationship. Every object has a single parent, and may or may not have one or more children.

オブジェクトまたはオブジェクトの集合が相互に関連してどのように動くかをどうアプリ内でのオブジェクトを整理します。オブジェクトは互いに独立して移動することができ、またはそれらの動きは、そのコンテナに拘束し、依存することができます。コンテナおよびオブジェクトは、親子関係をもっています。すべてのオブジェクトは、単一の親を持ち、または1つ以上の子供を持っている場合もあるし持っていない場合もあります。

Children inherit transformation properties from their parent, such as position, rotation, scale, and elevation. For example, in the case of a scrolling card collection where all cards move together, the cards are siblings and they are all children of the card collection container that handles the scrolling movement.

子要素は、そのような位置、回転、スケール、標高など親から継承されたプロパティを保有します。たとえば、すべてのカードが一緒に移動した場合やスクロールカードコレクションの場合には、カードが兄弟であり、それらはスクロール移動を処理しカードは収集コンテナのすべての子に継承されます。

The hierarchy of parents and children determines how objects and groups of objects interact with one another. For example, child objects have minimal z-axis separation from their parent; other objects do not get inserted between parents and children.

親と子の階層は、オブジェクトやグループが互いにどのように相互作用するかを決定します。例えば、子オブジェクトは、親からの最低限のz軸方向での幅を持ちます。親子以外のオブジェクトは親と子の間に入り込むことができません。