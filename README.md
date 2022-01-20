# splitTitle

**This is not a NPM package, this is simple snipet to copy paste it.**

This code demonstrate not a perfect, but simple and useful way of how to split words in title pretty

> Just copy the code below and paste it to your project.

```ts
/**
 * Split text to binary tree for more beautiful text wrapping
 * @example
 * return <h1>{splitTitle(props.titile)}</h1>
 * @see {@link github.com/artalar/splitTitle}
 */
export function splitTitle(text: string) {
  if (text.length < 5 || !text.includes(" ")) {
    return text;
  }
  const median = Math.floor(text.length / 2);
  for (let step = 0; step < median; step++) {
    for (const i of [median - step, median + step]) {
      if (text[i] === " ") {
        return (
          <span style={{ display: "inline-block" }}>
            {splitTitle(text.substring(0, i))}{" "}
            {splitTitle(text.substring(i + 1))}
          </span>
        );
      }
    }
  }
}
```

## Example

[![codesandbox with splitTitle example](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/title-splitting-sw6dj)

<img width="834" alt="CleanShot 2022-01-20 at 17 58 13@2x" src="https://user-images.githubusercontent.com/27290320/150363785-f9b0a88f-7df1-48b4-975a-ea54dc9a653f.png">

<img width="742" alt="CleanShot 2022-01-20 at 17 58 51@2x" src="https://user-images.githubusercontent.com/27290320/150363833-a90a3ec4-351f-4d20-96b2-b70d7f9c223a.png">

<img width="646" alt="CleanShot 2022-01-20 at 17 59 12@2x" src="https://user-images.githubusercontent.com/27290320/150363863-2ea42f3d-4625-4cdf-b071-5161d0d895bc.png">

<img width="436" alt="CleanShot 2022-01-20 at 17 59 30@2x" src="https://user-images.githubusercontent.com/27290320/150363881-81fb19c0-0875-4ce8-855b-9c98360bc47b.png">
