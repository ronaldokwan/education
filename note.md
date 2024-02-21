actor (M to M) Movie, table junction

ActorHasMovie

Actor 1 to Many ActorHasMovie
Movie 1 to Many ActorHasMovie

many to many

junction.js

movie_id:{
references:{
model:"Movies",
key:"id"
}
}
actor_id:{
references:{
model:"Actors",
key:"id"
}
}

MovieHasActors.belongsTo(models.Actor, {
foreignKey: "actor_id"
})
MovieHasActors.belongsTo(models.Movie, {
foreignKey: "movie_id"
})

actor.js

Actor.belongsToMany(models.Movie,{through:"ActorHasMovies",foreignKey:"actor_id"})

movie.js

Movie.belongsToMany(models.Actor,{through:"ActorHasMovies",foreignKey:"movie_id"})

double one to many (include -> include)

actor.js

Actor.hasMany(models.ActorHasMovie,{foreignKey:"actor_id"})

movie.js

Movie.hasMany(models.ActorHasMovie,{foreignKey:"movie_id"})

junction.js

ActorHasMovie.belongsTo(models.Actor,{foreignKey:"actor_id"})
ActorHasMovie.belongsTo(models.Movie,{foreignKey:"movie_id"})

super many to many

chartjs,nodemailer,stripejs,multer,easyInvoice,qrcode,puppeteer
