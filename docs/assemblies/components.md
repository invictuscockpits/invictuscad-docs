# Components and Connections

## Components

**Make Component** turns bodies into a component; **Edit Component** opens it for changes in
place, in the context of the rest of the design. Place more **instances** of a component and each
one updates when the component changes. Move, copy or **ground** (fix in place) instances.

## Connections

Connect instances so they position each other:

| Type | Allows |
|---|---|
| Fixed | No motion |
| Hinge | Rotation about an axis |
| Slider | Movement along an axis |
| Cylindrical | Rotation and sliding on one axis |
| Planar | Sliding in a plane |
| Ball | Rotation about a point |

## Linked parts

**Link to File** brings in a part from another `.ivc` file. It stays linked: **Update Links** pulls
in changes, and **Embed** breaks the link and keeps a copy in this file.
