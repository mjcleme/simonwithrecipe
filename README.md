# simonwithrecipe

Here are the changes to add a button and a route and a database entry

```
Authenticated.jsx

function recipe() {
    fetch(`/api/auth/recipe`, {
      method: 'post',
    })
      .catch(() => {
        // recipe failed. Assuming offline
      })
      .finally(() => {
        console.log('recipe requested');
      });
  }

return (
    <div>
      <div className='playerName'>{props.userName}</div>
      <Button variant='primary' onClick={() => navigate('/play')}>
        Play
      </Button>
      <Button variant='secondary' onClick={() => logout()}>
        Logout
      </Button>
      <Button variant='primary' onClick={() => recipe()}>
        Recipe
      </Button>
    </div>
  );

Index.js

// Recipe - token if stored in cookie
apiRouter.post('/auth/recipe', async (req, res) => {
  console.log('Recipe requested');
  const user = await DB.foobar("recipe");
  res.status(204).end();
});

database.js
async function foobar(recipe) {
  console.log(foobar);
  await recipeCollection.insertOne({recipe});
}

module.exports = {
  getUser,
  getUserByToken,
  addUser,
  updateUser,
  addScore,
  getHighScores,
  foobar,
};

```
