# Phase 1 - Ephemeral State

A StatelessWidget is used when a widget does not need to manage changing data after it is built. A StatefulWidget is used when the widget contains data that can change while the application is running.

The FavoriteButton needs to be a StatefulWidget because its _isFavorited value changes whenever the user presses the button. Calling setState() tells Flutter that the state changed and causes the widget to rebuild with the correct icon and color. A StatelessWidget would not work for this because it does not have mutable state that can be updated with setState().

# Phase 2 - Profile Input Form & Validation

The GlobalKey<FormState> gives the program access to the current state of the Form widget. This allows the program to validate all of the fields in the form from the Save Profile button.

When _formKey.currentState!.validate() is called, Flutter runs the validator function for each TextFormField connected to the form. If a validator returns an error message, Flutter knows that the input is invalid and rebuilds the form to display the error message below the field. If the validator returns null, the input is considered valid and the program can continue with the save action.

# Phase 3 - Lifting State Up

It was necessary to move the username state from ProfileForm up to ProfileScreen because more than one widget needs access to that data. The ProfileForm changes the username, while the UserBanner needs the username so it can display the updated greeting. Keeping the state in their common parent allows both widgets to work with the same value.

The FavoriteButton state should stay inside the FavoriteButton because no other widget needs to know whether the profile is favorited. Keeping this state local makes the code simpler and avoids moving state higher in the widget tree when it is not necessary.