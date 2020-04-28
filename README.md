## Exercise 1 Analysis

The problem for this exercise was the item price covering the phrase "One-Time Payment" when zooming in or zooming out extremely far.
The reason I found for this was that a height of 22px was set for the Price Title's CSS, by removing this it would scale correctly with the value.

## Exercise 2 Analysis

The problem for this exercise was, when zooming in on the page until one package-container was viewable per page, it would not be centered. The reason is the object's container was set to display: flex, but the attribute align-items wasn't set. When the attribute isn't set it defauls to stretch, which will attempt to fill the entire column with the block, but the block also had a max-width set. This meant that after if hit that max-width it would stop expanding and stay justified to the left. To fix this problem I added a new attribute to the container, align-items: center;, so that when the max-width was hit, it would still center the block.

## Exercise 3 Analysis

The problem for this exercise was a bug in the itemIncluded method that prevented the correct items from being crossed out. The issue in the method was broken into two parts. The first issue was in the first conditional of the method. It was checking that the item was a boolean value, but the item was an object that contained a boolean attribute. I modified that check to verify that the attribute, item.included, was a boolean and not the item itself. The second issue was that the method was comparing the included attribute on the item to a string false, but the attribute was already a boolean and so it was attempting to compare a boolean with a string of the boolean. To fix this I modified it to check the item's included attribute with the boolean false.

## Exercise 4 Analysis

The problem for this exercise was to refactor the code in the Packages.vue file as I see fit to increase clarity and reusability. The first step I took in this was to abstract any code around each individual package block into a separate component. The next refactor was to remove unnecessary data. I noticed there were a lot of unused keys on the data that could be removed, so I checked all attributes from the package that were used and removed almost anything else. I noticed some keys in the data that weren't used but might be helpful to provide context, like the name key in the thumbnails. I left those in, because it would be difficult to understand which thumbnail it was referencing if not. After that I went through the data and cleaned up any stylistic issues I saw, like incorrect spacing for nested hashes. I then went through and removed all the css that wasn't being used. Any further refactors would be to the newly created component PackageBlock to abstract it out further into smaller components.

## Bonus

The problem for this exercise was that an image would not be selected and displayed in the larger view if the page had been scrolled or zoomed. This problem was caused by lazy-loading the ImagePresenter component. I fixed the issue by removing it, so now the images will always be displayed and selected when clicked. The lazy-component was removing all listeners after being triggered for the first time, so when the page was scrolled or resized the listeners were removed and clicking the image no longer did anything.