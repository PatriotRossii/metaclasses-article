<table>
<tr>
<td> perms </td> <td> directory_options </td> <td> perm_options </td>
</tr>
<tr>
<td>

```c++
enum class perms: unsigned {
  // ...
  owner_read = 0400,
  owner_write = 0200,
  owner_exec = 0100,
  owner_all = 0700,
  // ...
};

inline constexpr perms operator&(perms lhs, perms rhs) {
  return static_cast<perms>(
      static_cast<unsigned>(lhs) & static_cast<unsigned>(rhs)
    );
}

inline constexpr perms operator|(perms lhs, perms rhs) {
  return static_cast<perms>(
    static_cast<unsigned>(lhs) | static_cast<unsigned>(rhs)
  );
}

inline constexpr perms operator^(perms lhs, perms rhs) {
  return static_cast<perms>(
    static_cast<unsigned>(lhs) ^ static_cast<unsigned>(rhs)
  );
}

inline constexpr perms operator~(perms lhs) {
  return static_cast<perms>(~static_cast<unsigned>(lhs));
}

inline perms& operator&=(perms& lhs, perms rhs) {
  return lhs = lhs & rhs;
}

inline perms& operator|=(perms& lhs, perms rhs) {
  return lhs = lhs | rhs;
}

inline perms& operator^=(perms& lhs, perms rhs) {
  return lhs = lhs ^ rhs;
}
```

</td>

<td>

```c++
enum class directory_options: unsigned char {
  none = 0,
  follow_directory_symlink = 1,
  skip_permission_denied = 2
};

inline constexpr directory_options operator&(directory_options lhs, directory_options rhs) {
  return static_cast<directory_options>(
    static_cast<unsigned char>(lhs) & static_cast<unsigned char>(rhs)
  );
}

inline constexpr directory_options operator|(directory_options lhs, directory_options rhs) {
  return static_cast<directory_options>(
      static_cast<unsigned char>(lhs) | static_cast<unsigned char>(rhs)
  );
}

inline constexpr directory_options operator^(directory_options lhs, directory_options rhs) {
  return static_cast<directory_options>(
    static_cast<unsigned char>(lhs) ^ static_cast<unsigned char>(rhs)
  );
}

inline constexpr directory_options operator~(directory_options lhs) {
  return static_cast<directory_options>(~static_cast<unsigned char>(lhs));
}

inline directory_options& operator&=(directory_options& lhs, directory_options rhs) {
  return lhs = lhs & rhs;
}

inline directory_options& operator|=(directory_options& lhs, directory_options rhs) {
  return lhs = lhs | rhs;
}

inline directory_options& operator^=(directory_options& lhs, directory_options rhs) {
  return lhs = lhs ^ rhs;
}




```

</td>

<td>

```c++
enum class perm_options: unsigned char {
  replace = 1,
  add = 2,
  remove = 4,
  nofollow = 8
};

inline constexpr perm_options operator&(perm_options lhs, perm_options rhs) {
  return static_cast<perm_options>(
    static_cast<unsigned>(lhs) & static_cast<unsigned>(rhs)
  );
}

inline constexpr perm_options operator|(perm_options lhs, perm_options rhs) {
  return static_cast<perm_options>(
    static_cast<unsigned>(lhs) | static_cast<unsigned>(rhs)
  );
}

inline constexpr perm_options operator^(perm_options lhs, perm_options rhs) {
  return static_cast<perm_options>(
    static_cast<unsigned>(lhs) ^ static_cast<unsigned>(rhs)
  );
}

inline constexpr perm_options operator~(perm_options lhs) {
  return static_cast<perm_options>(~static_cast<unsigned>(lhs));
}

inline perm_options& operator&=(perm_options& lhs, perm_options rhs) {
  return lhs = lhs & rhs;
}

inline perm_options& operator|=(perm_options& lhs, perm_options rhs) {
  return lhs = lhs | rhs;
}

inline perm_options& operator^=(perm_options& lhs, perm_options rhs) {
  return lhs = lhs ^ rhs;
}



```

</td>

</tr>
<tr>
</tr>
</table>
