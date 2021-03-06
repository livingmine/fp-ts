---
id: Witherable
title: Module Witherable
---

[Source](https://github.com/gcanti/fp-ts/blob/master/src/Witherable.ts)

## Type classes

### Witherable

_type class_

_since 1.7.0_

_Signature_

```ts
interface Witherable<T> extends Traversable<T>, Filterable<T> {
  /**
   * Partition a structure with effects
   */
  wilt: Wilt<T>

  /**
   * Filter a structure  with effects
   */
  wither: Wither<T>
}
```

_Description_

`Witherable` represents data structures which can be _partitioned_ with effects in some [Applicative](./Applicative.md) functor.

`wilt` signature (see [Compactable](./Compactable.md) `Separated`):

```ts
<F>(F: Applicative<F>) => <RL, RR, A>(wa: HKT<W, A>, f: (a: A) => HKT<F, Either<RL, RR>>) => HKT<F, Separated<HKT<W, RL>, HKT<W, RR>>>
```

`wither` signature:

```ts
<F>(F: Applicative<F>) => <A, B>(ta: HKT<W, A>, f: (a: A) => HKT<F, Option<B>>) => HKT<F, HKT<W, B>>
```
