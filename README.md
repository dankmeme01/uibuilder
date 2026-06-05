# UIBuilder

> [!WARNING]
> This is a fork of UIBuilder that is maintained and actively used in Globed. It is tailored for my needs and may not be fully suitable for use in other projects.

Currently it features a couple things over the mainline library:
* Better performance of certain functions
* More Geode utils (e.g. geode::Function, geode::Button)
* Some new helper methods (e.g. `intoCircle`)
* Allows you to easily extend and add your own methods to `Build`:

```cpp
template <>
struct uibuilder::BuildExtend<ObjectDisplay> : BuildBase<ObjectDisplay> {
    using BuildBase<ObjectDisplay>::BuildBase;

    auto caption(ZStringView text) {
        m_item->setCaption(text);
        return Build<ObjectDisplay>(*this);
    }
};

// ...

Build(ObjectDisplay::create(obj))
    .caption("hii")
    .scale(1.5f)
    .parent(m_objsContainer)
    .collect();
```


Header-only UI Builder class for Geometry Dash. Supports any modding library as long as it has all of the functions defined. Can be easily integrated via CPM if you wish.

## Example Projects that use UIBuilder

- [Icon Profile by Capeling](https://github.com/Capeling/icon-profile-geode/)
- [List Buttons by Me](https://github.com/camila314/geode-mods/tree/main/list-buttons)
- [BetterMenuMod by MuhXd](https://github.com/MuhXd/BetterMenuMod)
