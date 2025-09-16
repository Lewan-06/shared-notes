## Bounded contexts
Actions per user group
### User accounts
- Make APC account
- Make user account
- Start premium 
- Stop premium
- Start family plan
- Stop family plan
- Update user account settings
- Update APC account settings
- Set user account monthly billing
- Set user account yearly billing
### Friends
- Send user request
- Accept user request
- Start shared jam
### Songs & podcasts
- Upload song
- Upload podcast
- Divide money
### Playlists & library
- Make playlist
- Like playlist
- Shuffle songs
### Ads
- Upload add
- Show add
- Focus audience
- Set monthly billing
- Set yearly billing

I have decided the bounded contexts by identifying the possible actions we can perform on Spotify according to the description. These we then group and call the bounded contexts.
## Alternatives
The billing settings I could have moved to a separate bounded context possibly and dividing the money so royalties as well. Since each billing type is so closely related to a specific domain context, it makes more sense to add them to their corresponding domain.

### Core, Generic or Support
The main function of the platform is listening songs & podcasts, so I will make songs part of core. User settings are important, but parts are less important making them part of generic. Friends are also part of generic as they are not strictly essential to the functionality of listening to songs. Advertisements are supports as they are not part of the functionality, but necessary for earning revenue. Playlists and library are directly supporting the song listening functionality so those are generic.

Core: songs & podcasts
Generic: user accounts, friends, playlists & library
Support: Ads

## Organisation patterns
![[IMG_7735 2.jpg]]


Ads - Songs & podcasts = customer/supplier: the adds need to be built around the song and podcasts listening functionality.

User accounts - Playlists & library = shared kernel: both parties depend on each other since a playlist is created based on a user's settings and preferences. While a user also must be able to create a song.

Friends - User accounts = customer/supplier: the friends functionality is built around the user accounts and thus is there is a one sided dependency.


## Refactoring
![[IMG_7736.jpg]]


I have created a "bulk manage" boundary context for these bulk actions. The connection from this context to playlists & library as well as user account is customer-supplier. This is because the bulk manage context fully relies on the other codebases. All the actions have been added to this separate context.