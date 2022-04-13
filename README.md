
Assignment 3

Jag började med att lägga till nya widgets til layouten. Dessa widgets var EditText, Button och ImageView.
Tanken var att det skulle bli som en log in sida där det är en bild på en avatar. Och under bilden så finns en TextView widget som ber användaren att skriva in sitt användarnamn.
Och under TextView så lades det till en EditText där användaren skulle kunna lägga in sitt användarnamn.
Och sist en knapp användaren kan trycka på för att logga in.
Koden för detta ser ut såhär:

```
    <Button
        android:id="@+id/Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button" />

    <EditText
        android:id="@+id/EditText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="EditText" />

    <ImageView
        android:id="@+id/ImageView"
        android:layout_width="184dp"
        android:layout_height="194dp"
        tools:srcCompat="@tools:sample/avatars" />
```

När dessa widgets var på plats så ändrades texterna i EditText, TextView och button så de passade till den tänkta log in sidan.
Och sedan så ändrade jag namnen på de id som fanns i widgetsen.
Detta är koden som ändrades.

```
    <TextView
        android:id="@+id/signin_label"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Ange ditt användarnamn i textrutan"

    <Button
        android:id="@+id/signin_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Logga in"

    <EditText
        android:id="@+id/signin_name"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="Ange användarnamn"

    <ImageView
        android:id="@+id/signin_avatar"
        android:layout_width="184dp"
        android:layout_height="194dp"
        tools:srcCompat="@tools:sample/avatars" />
```

Och det sista som gjordes var att positionera alla widgets så att de låg centralt på sidan och under/över varandra så att de hänger ihop.

ImageView:
Jag började med att positionera ImageView genom att lägga till en layout_constraintBottom_toTopOf="@id/signin_label" som gör att den positioneras över och följer TextView widgeten.
Sedan för att positionera den centralt över TextView widgeten så lades koden layout_constraintStart_toEndOf="@id/signin_label" och layout_constraintStart_toStartOf="@id/signin_label" till.

EditText:
Jag ville ha EditText widgeten under TextView så för att få till detta så lades layout_constraintTop_toBottomOf="@id/signin_label" som gör att EditText hamnar under och följer TextView.
Sedan likt ImageView för att centrera EditText så lades layout_constraintStart_toEndOf="@id/signin_label" och layout_constraintStart_toStartOf="@id/signin_label" till.

Button:
Positioneringen för button ville jag ha under EditText så den ligger precis under där användaren lägger in sitt användarnamn. Detta gjordes med layout_constraintTop_toBottomOf så att button hamnar under EditText.
Och likadant som de andra widgets för att centrera Button så lades layout_constraintStart_toEndOf och layout_constraintStart_toStartOf till.

TextView
Det som gjordes för positioneringen av TextView var att den flyttades med margin. Detta gjordes genom att i activity_main.xml flyttades den i split-vyn och en margin lades till automatiskt.
Den margin som lades till var layout_constraintHorizontal_bias="0.572". Vilket gjorde att den flyttades lite till höger så att det ligger i mitten på sidan.

```
    <TextView
        android:id="@+id/signin_label"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Ange ditt användarnamn i textrutan"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintHorizontal_bias="0.572"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/signin_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Logga in"
        app:layout_constraintTop_toBottomOf="@id/signin_name"
        app:layout_constraintStart_toStartOf="@id/signin_name"
        app:layout_constraintStart_toEndOf="@id/signin_name"/>

    <EditText
        android:id="@+id/signin_name"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="Ange användarnamn"
        app:layout_constraintTop_toBottomOf="@id/signin_label"
        app:layout_constraintStart_toEndOf="@id/signin_label"
        app:layout_constraintStart_toStartOf="@id/signin_label"/>

    <ImageView
        android:id="@+id/signin_avatar"
        android:layout_width="184dp"
        android:layout_height="194dp"
        app:layout_constraintBottom_toTopOf="@id/signin_label"
        app:layout_constraintStart_toEndOf="@id/signin_label"
        app:layout_constraintStart_toStartOf="@id/signin_label"
        tools:srcCompat="@tools:sample/avatars" />
```
