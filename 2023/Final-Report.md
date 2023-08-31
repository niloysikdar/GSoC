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

- [Project Proposal]()

## Project Repository

- [sugarlabs/musicblocks-v4](https://github.com/sugarlabs/musicblocks-v4)

## GSoC Blogs

- [GSoC 2023 with Sugar Labs | Week 1-5 | Music Blocks (v4) project updates](https://musicblocks.net/2023/07/03/gsoc-2023-with-sugar-labs-week-1-5-music-blocks-v4-project-updates)
- [GSoC 2023 with Sugar Labs | Week 6 | Music Blocks (v4) project updates](https://musicblocks.net/2023/07/12/gsoc-2023-with-sugar-labs-week-6-music-blocks-v4-project-updates)
- [GSoC 2023 with Sugar Labs | Week 7-11 | Music Blocks (v4) project updates](https://musicblocks.net/2023/08/25/gsoc-2023-with-sugar-labs-week-7-11-music-blocks-v4-project-updates)

<br />

## Work Summary

We started the React Email Project from scratch this summer. From initializing the package, to implementing CI/CD, creating components and utility methods, writing tests and stories using Storybook, creating documentation, and finally publishing the package on NPM - we did all of these in just 13 weeks. We also created a docs page using Docusaurus and deployed it on Netlify along with the Storybook and TypeDoc documentation. Also, we have used TypeScript for the whole project to make it more robust, reliable, and typesafe for the users. We have also used ESLint and Prettier for linting and formatting the codebase. We started by finalizing the Task breakdown and creating the project roadmap. We also finalized the approach for creating the components and utility methods in several meetings. I learnt a lot of new things while working on this project under the guidance of my mentor. You can find the detailed work summary in the [GSoC Blogs](#gsoc-blogs) and the [Project Board](https://github.com/orgs/leopardslab/projects/3).

## Project Timeline

### May 4 - 28

- Community Bonding Period, Task Breakdown, Project Roadmap, and Approach Finalization

### May 29 - August 28

- Coding Period

<br />

## Assigned Issues

| Title                                                                         | Link                                                           |
| ----------------------------------------------------------------------------- | -------------------------------------------------------------- |
| List properties for defining and customising bricks                           | [#327](https://github.com/sugarlabs/musicblocks-v4/issues/327) |
| Implement a class-based inheritance structure for bricks                      | [#328](https://github.com/sugarlabs/musicblocks-v4/issues/328) |
| Implement final classes for the 4 brick types:                                |                                                                |
| Data, Expression, Statement, and Block and create React components for bricks | [#329](https://github.com/sugarlabs/musicblocks-v4/issues/329) |
| Calculate bounding boxes in brick path utility                                | [#341](https://github.com/sugarlabs/musicblocks-v4/issues/341) |
| Render a dummy workspace with the different types of bricks, and tree data    | [#360](https://github.com/sugarlabs/musicblocks-v4/issues/360) |

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
