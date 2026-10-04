# Phase 1 - Ephemeral State

A StatelessWidget is used when a widget does not need to manage changing data after it is built. A StatefulWidget is used when the widget contains data that can change while the application is running.

The FavoriteButton needs to be a StatefulWidget because its _isFavorited value changes whenever the user presses the button. Calling setState() tells Flutter that the state changed and causes the widget to rebuild with the correct icon and color. A StatelessWidget would not work for this because it does not have mutable state that can be updated with setState().