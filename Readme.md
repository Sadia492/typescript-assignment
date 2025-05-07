# What are some differences between interfaces and types in TypeScript?

In TypeScript, both interfaces and types are used to define the shape of data, like what properties an object should have. Interfaces are mainly used for objects and can be extended to add more properties. Types are more flexible. We can use them for objects, but also for combining types using union (|) and intersection (&).

Interfaces act like rules that objects must follow. We can add more rules to an interface later by writing it again with extra properties. But with types, once we define them, we can't add more to them in the same way.

Types are more flexible and can be used to create mapped types, which interfaces cannot. Additionally, types can be used for primitives, unions, and tuples, whereas interfaces cannot.

In TypeScript, We can write the same interface more than once, and TypeScript will combine them into one. But if we try to do that with a type, we'll get an error. Types don’t allow merging like interfaces do.

Interfaces can be used to extend or implement other types, including union types. But with type, We can't do that in the same way. Interfaces give us more flexibility when building on top of other types.

For intersection types, types can create intersection types by combining multiple types, but interfaces cannot.

In summary, the choice between interfaces and types often depends on the specific needs of the project, such as the necessity for extending types or the need for unions and intersections.

---

# What is the use of the keyof keyword in TypeScript? Provide an example.

The keyof keyword in TypeScript lets us to get all the keys (property names) of an object type. It gives us a list of those keys as a type. This is really helpful when we want to work with object properties in a safe way. So TypeScript can check that we are using the right keys and help prevent mistakes in our code.

Let's say we have a simple `User` type:

```ts
type User = {
  id: number;
  name: string;
  email: string;
};
```

If we write:

```ts
type UserKeys = keyof User;
```

Then `UserKeys` becomes:

```ts
type UserKeys = "id" | "name" | "email";
```

This keyword helps in reducing bugs and improving autocomplete suggestions in our editor. Keyof might seem small, but it’s a powerful tool that helps us write cleaner, safer TypeScript code. It’s one of those things that feels simple but opens the door to writing much better code once we get the hang of it.
