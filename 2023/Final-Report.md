# Music Blocks v4 Project Builder Integration

## Final Work Report for the Google Summer of Code 2023 under `Sugar Labs` for the Music Blocks v4 project

<p align="center">
<img src="https://github.com/niloysikdar/GSoC/assets/58071992/e7549f21-2fc3-4947-935c-3ce3fbddbf94" height="250px">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src="https://github.com/niloysikdar/GSoC/assets/58071992/3730cd33-830d-4be7-b5a6-4f5d7bd10856" height="250px">
</p>

## Contributor Info

<div container>
<table>

<tr>
<td width="400px">
&#8226; Name - Niloy Sikdar <br />
&#8226; Organization - <a href="https://github.com/sugarlabs" target="_blank">Sugar Labs</a><br />
&#8226; Email - <a href="mailto:niloysikdar30@gmail.com" target="_blank">niloysikdar30@gmail.com</a><br />
&#8226; GitHub - <a href="https://github.com/niloysikdar" target="_blank">niloysikdar</a><br />
&#8226; Linkedin - <a href="https://www.linkedin.com/in/niloysikdar" target="_blank">Niloy Sikdar</a><br />
&#8226; Twitter - <a href="https://twitter.com/niloysikdar_" target="_blank">niloysikdar_</a><br />
&#8226; Medium - <a href="https://niloysikdar.medium.com" target="_blank">niloysikdar</a><br />
</td>
<td>
<a href="https://github.com/niloysikdar"><img src="https://i.imgur.com/wDO1nLU.png" height="180px" width="180px;" alt="Niloy Sikdar"/></a>
</td>
</tr>
</table>
</div>

## Mentors' Info

- **Mentor:** [Anindya Kundu](https://github.com/meganindya)

- **Assisting Mentor:** [Walter Bender](https://github.com/walterbender)

<br />

## Project Details

The **Music Blocks v4** project is “_a complete overhaul of the original Music Blocks project_”, which was derived from the [Turtle Blocks](https://github.com/sugarlabs/turtleblocksjs) project. The existing implementation ([Music Blocks](https://github.com/sugarlabs/musicblocks)), which started in 2015 using native Vanilla JavaScript, lacks modern front-end tooling and ecosystem standards, leading to difficulties in maintenance and subpar performance. The v4 project uses improved application architecture, modern tools (such as _Vite, ESLint, Prettier, Docker, Jest, Cypress, etc._), better languages (_TypeScript and Sass_), and libraries (_React for UI rendering_). This will significantly enhance the overall developer and user experience, maintainability, and performance. The project focuses on implementing one of the main features of Music Blocks, the "**Project Builder**", which is currently missing in the new version (v4). The Project Builder is a graphical block manager module which is used to create Music Blocks programs, including interactive blocks like _Start, Rhythm, Note, Pitch, Instrument_, and many more. These blocks can be dragged, dropped, and clicked to perform actions or open context menus. By implementing the Project Builder feature, users will be able to create different musical patterns seamlessly. This will bring the v4 project on par with the capabilities of the old version and provide a more accessible, efficient, and user-friendly application for users to create music through an interactive web application.

<br />

## GSoC Project Page

- [GSoC 2023 with Sugar Labs - Music Blocks v4](https://summerofcode.withgoogle.com/programs/2023/projects/Rti7iZKG)

## GSoC Project Proposal

- [Project Proposal](./accepted-proposal.pdf)

## Project Repository

- [sugarlabs/musicblocks-v4](https://github.com/sugarlabs/musicblocks-v4)

## GSoC Blogs

- [GSoC 2023 with Sugar Labs | Week 1-5 | Music Blocks (v4) project updates](https://musicblocks.net/2023/07/03/gsoc-2023-with-sugar-labs-week-1-5-music-blocks-v4-project-updates)
- [GSoC 2023 with Sugar Labs | Week 6 | Music Blocks (v4) project updates](https://musicblocks.net/2023/07/12/gsoc-2023-with-sugar-labs-week-6-music-blocks-v4-project-updates)
- [GSoC 2023 with Sugar Labs | Week 7-11 | Music Blocks (v4) project updates](https://musicblocks.net/2023/08/25/gsoc-2023-with-sugar-labs-week-7-11-music-blocks-v4-project-updates)

<br />

## Work Summary

### • Creating SVGs for Bricks

Creating SVGs for bricks was a challenging task. I had to create SVGs for 4 different types of bricks and each brick had 8 different states (`hasNest`, `hasNotchArg`, `hasNotchInsTop`, `hasNotchInsBot`, `scale`, `nestLengthY`, `innerLengthX`, `argHeights`). I used an online tool [https://yqnn.github.io/svg-path-editor](https://yqnn.github.io/svg-path-editor) to visualize the path data and create the SVGs. I also used the SVGs from the old version of Music Blocks as a reference. Each one of the SVGs was created by hand and it took a good amount of time to create them. We also needed to take care of the dimensions and each pixel for the SVGs as we needed to calculate the collision areas later on. We also created a script/utility function to generate the path of the SVGs using different argument values. Moreover, we also created different classes for the bricks and also some stories to visualise those paths along with the SVGs.

### • Implementing a class-based inheritance structure for 4 brick types: Data, Expression, Statement, and Block and create React components for bricks

We implemented a class-based inheritance structure for bricks. We created a base class `BrickModel` and then created 4 different classes for the different types of bricks. I created different public getter methods for the bricks to get the path, collision area, and other information; and implemented the missing abstract methods. I also created separate components for different types of bricks that used those classes to generate an instance object and use those data to render the bricks; and updated the storybook stories accordingly.

### • Implementing `extent` and `coords` for the args and notches

I implemented and fixed calculations to get the `extent` and `coords` values for the args and notches for all the bricks to detect the positions (x, y coordinates) and bounding boxes.

#### Objectives

- [x] Return these data for all bounding boxes
  - [x] `bBoxBrick`
  - [x] `bBoxNotchArg`
  - [x] `bBoxNotchInsTop`
  - [x] `bBoxNotchInsBot`
  - [x] `bBoxNotchInsNestTop`
  - [x] `bBoxArgs`
- [x] Change the types and classes of the bricks to expose args and notches' data using getter methods
- [x] Draw the bounding boxes (rectangles of different outline colours) for all of the args and notches over the bricks, to visually verify the calculations are correct (in the storybook)
- [x] Add missing tests inside `path.spec.ts`

**Here are some of the Storybook screenshots:**

<img src="https://github.com/sugarlabs/musicblocks-v4/assets/58071992/809363e0-2ea8-4a31-99a0-bcd107219524" width="400px" />
<img src="https://github.com/sugarlabs/musicblocks-v4/assets/58071992/69abc880-3c0f-4467-9eef-f43eaf85700c" width="400px" />
<img src="https://github.com/sugarlabs/musicblocks-v4/assets/58071992/8146fb0a-b369-4be8-b351-bfe33fd2b7c0" width="400px" />
<img src="https://github.com/sugarlabs/musicblocks-v4/assets/58071992/222315cf-a2fb-4a35-81a9-73c8cf754c8e" width="400px" />

### • Creating a dummy workspace inside the playground app

Using those different types of bricks (`"data" | "expression" | "statement" | "block"`), I created a dummy workspace inside our playground app (modules/code-builder/playground).

To do this, I first created a dummy `WORKSPACES_DATA` and assigned an initial tree state to maintain the state. It'll contain data about each brick and some other metadata. Also, each brick could contain children, which will be an array of different bricks. Here's a code snippet for the types.

```typescript
type InstanceMap = {
    data: ModelBrickData;
    expression: ModelBrickExpression;
    statement: ModelBrickStatement;
    block: ModelBrickBlock;
};

export type Brick = {
    id: string;
    type: TBrickType;
    instance: InstanceMap[TBrickType];
    surroundingBricks: { above: string; below: string };
    childBricks: string[];
    coords: TBrickCoords;
    children?: Brick[];
};

export const WORKSPACES_DATA: { id: string; data: Brick[] }[] = [
..........
]
```

I also created those different brick objects from the different brick classes/models and stored them inside the state. Then, I created a recursive functional React component `_RenderBricks_` that would recursively iterate through the overall tree state and render different types of bricks. I also created the `_BrickFactory_` wrapper component that’ll be responsible for returning and rendering the exact type of brick based on the `brickData` prop values. I also refactored and modified the brick components to accept the coords to properly position them inside the SVG (positioning the _g_ tags inside the SVG was another painful task. Finally, I used the CSS transform property with the translate values from the coords).

```typescript
function RenderBricks({ brickData }: { brickData: Brick }) {
  return (
    <>
      <BrickFactory brickData={brickData} />
      {brickData.children &&
        brickData.children?.length > 0 &&
        brickData.children.map((child) => (
          <RenderBricks key={child.id} brickData={child} />
        ))}
    </>
  );
}
```

So, after doing all of this, I successfully rendered the initial dummy workspace with different types of bricks nested into each other with different combinations and alignments. Here’s a picture of the workspace with a combination of different bricks nested and attached to each other rendering the tree state for the swimlane/workspace.

<img src="https://user-images.githubusercontent.com/58071992/254545160-2756a1bf-7115-4f81-a87c-82aca7649a1c.PNG" alt="Workspace Picture" height="300px"/>

The dummy workspace state can be found here: [modules/code-builder/playground/pages/WorkSpace/data.ts](https://github.com/sugarlabs/musicblocks-v4/pull/361/files#diff-e71c31ef248cfcc0233649e45d2a26476768c87177d173460967496ee79e2097)

### • Moving the Bricks and updating the position and state properly following the rules of Music Blocks

Now to do this, I needed to maintain some sort of centralized state where I could store all of the required dynamic data for each of the bricks along with their IDs (like coords). Also, I needed to update the data for the bricks while dragging them and needed to listen/subscribe to the changes for the data and update the UI according to that.

To do this, I used a simple and efficient library called [zustand](https://github.com/pmndrs/zustand) to create the store, update it, subscribe to the changes and update the React UI according to it. It’s so much simpler, more efficient and easy to use with less boilerplate code than other popular libraries like Redux (Oh, btw I hate Redux and love these proxy-based simple libraries for managing the global client-side state in React applications).

As per the plan, I created `BricksCoordsStore` and stored the coordinates of each brick respective to their IDs, and also attached two methods named `setCoords` (to update the coords value for each brick) and `getCoords` (to get the coords value of each brick).

I refactored and modified the `BrickFactory` component to use and encapsulate the move logic and update the positions and central state while keeping those brick components separate and out of any business logic. To achieve the best experience for the move logic while keeping it simple, accessible (**should work with keyboard, mouse and touch events**) and easy to use, I used the `useMove` hook from the “[**React Aria**](https://react-spectrum.adobe.com/react-aria)” open-source library.

Also, I created one bounding box indicating the workspace/swimlane and enclosed the move logic so that bricks wouldn’t go beyond that boundary. As I’m updating the global zustand store, and also listening to the changes, the UI is also getting updated/rerendered correctly.

Now comes the harder part, “calculating the move positions for other bricks following the rules of Music Blocks”. When we move one particular brick, we also need to calculate and find the other bricks whose positions need to be updated. For example, if I drag one brick, we also need to update the positions by the same distances of the bricks that are stuck below that specific brick and all of the children and their nested children and the below bricks – definitely some sort of recursive strategy.

That’s why I created the `getBelowBricksIds` utility function that uses the `recursiveSearch` function recursively to find all the IDs of the bricks whose positions needed to be updated when we drag any specific brick, and it returns the Array of IDs of those bricks.

```typescript
export function getBelowBricksIds(arr: Brick[], item: string): string[] {
  let result: string[] = [];

  function recursiveSearch(arr: Brick[], item: string) {
    arr.forEach((element, index) => {
      if (element.id === item) {
        arr.slice(index + 1, arr.length).map((el) => {
          result = result.concat(el.childBricks);
          result = result.concat(el.id);
        });
        return;
      }
      if (Array.isArray(element.children)) {
        recursiveSearch(element.children, item);
      }
    });
  }

  recursiveSearch(arr, item);
  return result;
}
```

Overall, when we move any specific brick, we need to update the position of that specific brick and move the same amount of position of the bricks which I’m getting from the `getBelowBricksIds` function. The code for this functionality can be found [here](https://github.com/sugarlabs/musicblocks-v4/tree/gsoc-2023/week-9-10/niloy).

Here everything comes together and is working perfectly.

https://github.com/niloysikdar/GSoC/assets/58071992/3d70f684-566e-4e48-ae07-9abbea3537c5


### • Detecting and updating the positions of collision areas for the bricks

We were already getting the positions of the bricks and updating them while moving them. Now we need to detect the collision areas for the bricks and update the positions of the collision areas accordingly. So, I rendered those collision areas inside the workspace (for visualization) and also updated their positions along with the bricks while moving them.

<img src="https://github.com/sugarlabs/musicblocks-v4/assets/58071992/7ef9758d-f798-4a58-89dd-40d945960d16" width="350px"  />
<img src="https://github.com/sugarlabs/musicblocks-v4/assets/58071992/5ad1cd12-e031-42e4-a0d2-3d8c91893462" width="350px"  />
<img src="https://github.com/sugarlabs/musicblocks-v4/assets/58071992/88798990-2abc-4640-b8e3-b0fe07e1b512" width="350px"  />
<img src="https://github.com/sugarlabs/musicblocks-v4/assets/58071992/f855908c-dd26-4e2a-8997-3ad7d878f743" width="350px"  />

<br/>

## Project Timeline

### May 4 - 28

- Community Bonding Period, Task Breakdown, Project Roadmap, and Approach Finalization

### May 29 - August 28

- Coding Period

<br />

## Assigned Issues

| Title                                                                                                                              | Link                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| List properties for defining and customising bricks                                                                                | [#327](https://github.com/sugarlabs/musicblocks-v4/issues/327) |
| Implement a class-based inheritance structure for bricks                                                                           | [#328](https://github.com/sugarlabs/musicblocks-v4/issues/328) |
| Implement final classes for the 4 brick types: <br/> Data, Expression, Statement, and Block and create React components for bricks | [#329](https://github.com/sugarlabs/musicblocks-v4/issues/329) |
| Calculate bounding boxes in brick path utility                                                                                     | [#341](https://github.com/sugarlabs/musicblocks-v4/issues/341) |
| Render a dummy workspace with the different types of bricks, and tree data                                                         | [#360](https://github.com/sugarlabs/musicblocks-v4/issues/360) |

## Pull Requests

| Title                                                                                                    | Link                                                         | Lines of Code Changed |
| -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ | --------------------- |
| feat(svg): add SVGs for the bricks                                                                       | [#332](https://github.com/sugarlabs/musicblocks-v4/pull/332) | `+1,942  −0`          |
| feat(code-builder): implement final classes and components for the 4 brick types                         | [#342](https://github.com/sugarlabs/musicblocks-v4/pull/342) | `+254  −56`           |
| Implement extent and coords for the args and notches                                                     | [#354](https://github.com/sugarlabs/musicblocks-v4/pull/354) | `+601  −143`          |
| feat(playground): dummy workspace inside playground                                                      | [#361](https://github.com/sugarlabs/musicblocks-v4/pull/361) | `+321  −21`           |
| Moving the Bricks and updating the position and <br/> state properly following the rules of Music Blocks | [#362](https://github.com/sugarlabs/musicblocks-v4/pull/362) | `+1,998  −245`        |
| feat(playground): detect and update positions of collision areas for the bricks                          | [#363](https://github.com/sugarlabs/musicblocks-v4/pull/363) | `+123  −44`           |

## What left

- Detect collision between bricks using those detected collision points and update (connect or disconnect bricks) the state of the workspace accordingly.

## Final Thoughts

I’m really grateful to my mentors, [Anindya Kundu](https://github.com/meganindya), [Walter Bender](https://github.com/walterbender), and [Devin Ulibarri](https://github.com/pikurasa) for their continuous support and guidance throughout the summer. I’m also thankful to the Sugar Labs community for giving me this opportunity to work on this project. I got some valuable insights into developing applications with the model-first approach. We'll keep iterating on this and hopefully complete the pieces so that we can release v4 soon.

Also, don’t forget to drop a star on the project GitHub repo! ⭐
Link: [https://github.com/sugarlabs/musicblocks-v4](https://github.com/sugarlabs/musicblocks-v4)

You can connect with me on [LinkedIn](https://www.linkedin.com/in/niloysikdar). Additionally, you can follow me on [GitHub](https://github.com/niloysikdar) and [Twitter](https://twitter.com/niloysikdar_), it will be appreciated.
