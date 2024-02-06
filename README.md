# AI-PlantCare-System
This project purpose a PlantCare system using SW-Prolog software. The proposed system can provide a robust platform for identifying plants diseases, recognizing pests, assessing nutrient deficiencies, and evaluating environmental stressors.

% Facts about the plants that are available in our database %Plants location whether its outdoor / indoor plant(tomato, outdoor).

plant(daisy, outdoor).

plant(basil, outdoor).

plant(sage, outdoor).

plant(potato_blight, outdoor).

plant(courgettes, both). plant(peas, outdoor). plant(apple, outdoor). plant(gooseberry, both). plant(hydrangea, outdoor). plant(rose,both). plant(honeysuckle, outdoor). plant(strawberries, indoor). plant(grapes,outdoor). plant(peony,outdoor). plant(blackberries, outdoor). plant(tomatoes,outdoor). plant(macadamia, outdoor). plant(passionfruit, outdoor). plant(mango,outdoor). plant(lychee,outdoor). plant(jasmine, outdoor). plant(morning_glory,outdoor). plant(olive_tree,outdoor). plant(hibiscus, outdoor). plant(olive_tree, outdoor). plant(mint, indoor). plant(parsley, indoor). plant(carnation, outdoor). plant(lily, outdoor). plant(daylilies, outdoor). plant(snapdragons, outdoor). plant(pines, outdoor). plant(czrnations, outdoor). plant(maple_tree, outdoor). plant(barberry, both). plant(lilac, outdoor). plant(linden, outdoor). plant(zinna, outdoor). plant(carrot, outdoor). plant(petunia, outdoor). plant(chrysanthemum, outdoor). plant(celery, outdoor). plant(figs, outdoor). plant(cucumbers, outdoor). plant(papers, outdoor). plant(cereals, outdoor). plant(forage_grasses, outdoor). plant(truf_grasses, outdoor). % Facts about the plant health disease % Fungus-Like disease problem(fungus_like,tomato). problem(fungus_like,daisy). problem(fungus_like,basil). problem(fungus_like,sage). problem(fungus_like,potato_blight).

% Powdery mildew(fungal disease) problem(powdery_mildew,courgettes). problem(powdery_mildew,peas). problem(powdery_mildew,apple). problem(powdery_mildew,gooseberry). problem(powdery_mildew,hydrangea). problem(powdery_mildew,rose). problem(powdery_mildew,honeysuckle).

% Grey mold disease problem(grey_mold,strawberries). problem(grey_mold,grapes). problem(grey_mold,gooseberries). problem(grey_mold,blackberries). problem(grey_mold,tomato).

% Black Spots disease problem(black_spots,peony). problem(black_spots,macadamia). problem(black_spots,passionfruit). problem(black_spots,mango). problem(black_spots,lychee). problem(black_spots,rose).

% Apohids disease problem(aphids,rose). problem(aphids,jasmine). problem(aphids,morning_glory). problem(aphids,olive_tree). problem(aphids,hibiscus). problem(aphids,mint). problem(aphids,parsley). problem(aphids,carnation). problem(aphids,lily).

% Rust disease problem(rust,daylilies). problem(rust,snapdragons). problem(rust,pines). problem(rust,rose). problem(rust,cznations).

% Vertcilliun Wilt disease problem(vertcillium_wilt,maple_tree). problem(vertcillium_wilt,barberry). problem(vertcillium_wilt,lilac). problem(vertcillium_wilt,linden). % Aster Yellows disease problem(aster_yellows,zinnia). problem(aster_yellows,carrot). problem(aster_yellows,petunia). problem(aster_yellows,chrysanthemum). problem(aster_yellows,celery).

% Mosaic Virus disease problem(mosaic_virus,figs). problem(mosaic_virus,tomato). problem(mosaic_virus,celery). problem(mosaic_virus,cucumbers). problem(mosaic_virus,peppers).

% Snow Mold disease problem(snow_mold,cereals). problem(snow_mold,forage_grasses). problem(snow_mold,turf_grasses).

% Recommendations "Treatments" for the plants based on the type of % diseases that a plant is pron to have them

%Fungus Like dissese treatments recommendation(fungus_like, '1- Avoid watering the plants from above to help keep the leaves dry. 2- Maximize airflow between the plants by giving them plenty of space. Tie vines to a trellis or cane support to help keep them off the ground.

3- If possible, bring the plants into the greenhouse to help prevent them from catching blight and ruining your produce.

4- remove the infected plants to prevent the spread of the fungus.' ).

%Powdery Mildew disease treatments recommendation(powdery_mildew, ' 1- Mulching, balanced feeding, and regular watering will help deter this unattractive disease.

2- On ornamental plants, spray the infected plant with Fungus Clear between April and September.

3- Prune out and dispose of infected shoots as soon as you see them, but don’t compost them. Raking up and destroying fallen infected leaves in autumn will help reduce the spread of spores.' ).

%Grey Mold Disease Treatments recommendation(grey_mold,' 1- Improving the ventilation in a greenhouse should help reduce the risk of mold.

2- Prune off any moldy leaves, buds, or fruit as soon as you see it and burn them, and don’t forget to clean your tools afterward. 3- Reduce overcrowding of plants allow for better ventilation and reduce humidity to prevent mould establishing.' ).

%Black Spots disease Treatments recommendation(black_spots, ' 1- The fungus overwinters in diseased canes and leaves, so remove both before winter. 2- Keep foliage clean and dry by mulching beneath plants, positioning roses where the morning sun will quickly evaporate dew, and watering at the roots rather than wetting the foliage.

3- Consider planting varieties of roses that are resistant to black spots.

4- Spray the plants with a fungicide to prevent black spots.' ).

%Aphids Disease Treatments recommendation(aphids, ' 1- Biological Control: Introduce natural predators or attract benefici insects.

2- Neem Oil: Disrupts aphid feeding and acts as a repellent.

Insecticidal Soaps: Break down aphid protective layers, causing dehydration.

3- Spraying with Water: Dislodge aphids with a strong water stream, focusing on leaf undersides.

4- Companion Planting: Plant species that repel aphids near susceptible crops.' ).

%Rust Disease Treatments recommendation(rust, ' 1- Purches a Fungicides and use it on the infected plant

2-Gather and destroy any infected plants to prevent the fungus from overwintering.

3- Pick or prune away any affected leaves as soon as you see them.' ).

% Verticillium Wilt Disease Treatments recommendation(verticillium_wilt, ' Unfortunately, there is no effective treatment for verticillium wilt.' ).

%Aster Yellows Disease Treatments recommendation(aster_yellows, ' Unfortunately, there is no effective treatment for aster yellows.' ).

%Mosaic Virus disease Treatments recommendation(mosaic_virus, 'Once a plant is infected, there are no cures for viral diseases, such as the mosaic virus.' ).

%Snow Mold disease Treatments recommendation(snow_mold, 'Gently take the affected areas of the lawn with a leaf rake.' ).

% Rules to identify the planst health issues identify_problem(Plant, Issue) :problem(Issue, Plant).

% Rules to provide a personalized recommendations (treatments) bases on % the plant diseases get_recommendation(Plant, Recommendation) :-

identify_problem(Plant, Issue), recommendation(Issue, Recommendation).

% Rules to determine if a plant is considered an indoor or outdoor % plant, base on the database of our system %If a Plants is Indoor is_indoor_plant(Plant) :plant(Plant, indoor),!.

%If a Plants is Outdoor is_outdoor_plant(Plant) :plant(Plant, outdoor).

%If a Plants is both outdoor and indoor is_both__plant(Plant):plant(Plant, both).

% Rule to find plants with a specific problem plants_with_problem(Problem, Plants) :setof(Plant, problem(Problem, Plant), Plants).

% Rule to find diseases for a specific plant diseases_for_plant(Plant, Diseases) :setof(Problem, problem(Problem, Plant), Diseases).

% Rules to assist users in improving plant care practices assist(Plant) :-

diseases_for_plant(Plant, Diseases), format('Plant: ~w~n', [Plant]), format('Diseases: ~w~n', [Diseases]). % Main menu that will be displayed on the uses screen main_menu:write(''),nl, write('--- Welcome to PlantCare ---'), nl, write(' A Plant Health Diagnosis Expert System'), nl, write('Our goal is to create a comprehensive and efficient tool that uses expert knowledge to diagnose and identify plant health issues. '), nl, write('Kindly select your choice from (1-5) '), nl, write('1. Identify the plant health issue'), nl, write('2. Get personalized recommendation'), nl, write('3. Determine the plant location (indoor, outdoor) '), nl, write('4. Identify the disease and all realted plants'), nl, write('5. Exit'), nl.

% Based on the user input of the numbers running from (1-4), each number will display a certain execution.

% Based on the user input of (1) and the plant name, the system will % retrieve information from the database and present all the issues the % plant can face.

selected_choice(1) :-

write('Enter the name of a plant: '), read(Plant), assist(Plant),!.

% Based on the user input of (2) and the plant name, the system will % retrieve information from the database and present its recommendation % or"Treatments " selected_choice(2) :-

write('Kindly Enter The Plant Name: '), read(Plant), get_recommendation(Plant, Recommendation), format('Recommendation for ~w: ~w~n', [Plant, Recommendation]),!.

%Based on the user input of(3) and the plant name, the system will % retrieve information from the database and present the type of the % plant base on the location (indoor,outdoor).

selected_choice(3) :-

write('Kindly Enter The Plant Name: '),

read(Plant), (is_indoor_plant(Plant) ->

format('~w is an indoor plant.~n', [Plant]) ; is_outdoor_plant(Plant) ->

format('~w is an outdoor plant.~n', [Plant]) ; is_both__plant(Plant) ->

format('~w is both indoor and outdoor plant.~n', [Plant]) ;

format('Location information not available for ~w.~n', [Plant]) ), !.

% Based on the user input of(4) and the plant disease name, the Expert % system will retrieve information from the database and present all % plants that have it in commen. selected_choice(4) :-

write('Enter the name of the plant disease: '), read(Disease), plants_with_problem(Disease, Plants), format('Plants with the problem ~w: ~w~n', [Disease, Plants]),!.

%Based on the user input of(5), the expert system is exiting. selected_choice(5) :write('The Expert System is Exiting... .') ,!.

%User enters a number outside the range of (1-5) selected_choice(_) :write('Invalid choice. Please try again.'), nl ,!.

% To Start Running The Program start :-

repeat, main_menu, read(Choice), selected_choice(Choice), Choice = 5,!.
