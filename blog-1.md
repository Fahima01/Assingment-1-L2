Topic: How do Pick and Omit utility types prevent code duplication while creating specialized "slices" of a master interface? Discuss how this keeps your code DRY (Don't Repeat Yourself).

When building large applications, we often create a big “master interface” like User, Product, or Ticket. But in many situations, we only need a few properties from that interface.

Instead of creating many repeated interfaces manually, TypeScript provides two utility types:

Pick → Select only specific properties
Omit → Remove specific properties

These help keep your code DRY (Don’t Repeat Yourself), cleaner, and easier to maintain.

1. Pick — Select Specific Properties

Use Pick when you want only certain fields from a larger interface.

Example
interface User {
  id: number;
  name: string;
  email: string;
  password: string;

  2. Omit — Remove Specific Properties

Use Omit when you want almost everything except a few fields.

Example

Using the same User interface:

type PublicUser = Omit<User, "password">;

Now PublicUser becomes:

{
  id: number;
  name: string;
  email: string;
}


