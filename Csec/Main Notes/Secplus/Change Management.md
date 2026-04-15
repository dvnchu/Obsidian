> [!info] Core Concept
> Clear policies are needed when making a change like a patch an upgrade or a modification in software

## Typical approval process
- complete the request forms
- Determine the purpose
- identify the scope of the change
- Schedule
- determine affected systems and impact
- Analyze risk associated with the change
- Get approval from the board
- Get end-user acceptance

It usually starts with the *owner* of the app or data, who donts perform the actual change; they manage the process

Stakeholders are impacted by a change

## Risks
- the fix doesnt actually fix anything
- it breaks something else
- operating systems failure
- data corruption

but you also have to consider the risk of not making a change:
- security vulnerability
- unavailability
- downtime to services

### Testing to avoid risks

**Sandbox testing environment** can be used, so we test before making a change to production
Also you can test the **backup** procedure.
You should always have a way to revert changes, and always have backups in case something goes wrong.


## Technical change management
The scope of a change is really important, as an approval is very specific.
sometimes scope can be expanded if needed.
Downtime is really usual
if you are in a 24hs you should try to prevent downtime, 
sometimes have a **backup system** thats automated so it switches back and forth.
with some changes you are required to reboot the system or a service 
Legacy apps add additional complexity as they are no longer maintained by the developer
Dependencies may cause necesity for a reboot in various apps as you make a change in something
Its really useful to have a version control * as well as an updated documentation




