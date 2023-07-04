## Todos
- [ ] Init Project
	- [ ] Create Repo
	- [ ] Create Project Structure
- [ ] Create mongo connections
- [ ] Create schemas

### DB Scheme
```json
// auth-user
{
	id: number,
	email: {
	value: string,
	verified: boolean,
	},
	name: string,
	phone: {
	countryCode: string,
	value: number,
	verified: boolean
	},
	password: encrypted-string,
	lastLogin: server-date-string,
	lastUpdated: server-date-string,
	//authToken: jwt-token-string
}
// auth-token
{
	id: number,
	userId: number,
	token: jwt-token-string,
}
// notes
{
	id: number,
	userId: number,
	notes: Array<number>,
}
// note_item 
{
	id: number,
	title: encrypted-string,
	content: encrypted-string,
	linkedNotes: Array<number>,
}
```
- Generate new auth token on every login ()
select all note from note_table where userid == authtoken.id

---
### Project Structure

```
project-root/
  |- src/
  |   |- modules/
  |   |   |- nute/
  |   |   |   |- controllers/
  |	  |.  |.  |.  |-nute.controller.ts
  |   |   |   |- services/
  |	  |.  |.  |.  |-nute.service.ts
  |   |   |   |- models/
  |	  |.  |.  |.  |-nute.model.ts
  |   |   |- user/
  |   |   |   |- controllers/
  |   |   |   |- services/
  |   |   |   |- models/
  |   |- app.js
  |- config/
  |- public/
  |- tests/
  |- package.json
  |- .env
  |- README.md
```