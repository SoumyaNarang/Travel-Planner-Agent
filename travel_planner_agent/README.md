Personal Travel Planner Agent

A travel-planning agent built with Google ADK and Gemini. Tell it where you want to go, for how many days, your budget and what you like, and it gives you a budget-friendly, day-wise itinerary.

If the destination, days or budget is missing, it asks a quick question first.

Setup
bash
python -m venv venv
venv\Scripts\activate           # Mac/Linux: source venv/bin/activate
pip install -r requirements.txt

Create a .env file in this folder with your Gemini API key (free at https://aistudio.google.com):

GOOGLE_GENAI_USE_VERTEXAI=FALSE
GOOGLE_API_KEY=your_api_key_here
Run

From the folder that contains travel_planner_agent/:

bash
adk web                          # browser chat UI
adk run travel_planner_agent     # terminal chat

In adk web, select travel_planner_agent and type your request.

How it works

agent.py defines one ADK agent (root_agent) using gemini-3.5-flash-lite. Its instruction tells it to understand the request, estimate the budget, recommend places and return a day-wise plan. Costs are rough model estimates, not live prices.

Example conversations

1. Jaipur

Me: I want to visit Jaipur for 3 days with a budget of ₹15,000. I like history and local food.

Agent: Understanding Your Request: You are planning a 3-day trip to Jaipur with a budget of ₹15,000, focusing on history and local food.

Trip Overview & Highlights: Welcome to the Pink City! This 3-day itinerary is custom-crafted to immerse you in Jaipur's royal heritage and vibrant culinary scene. You will explore magnificent forts, palaces, and bustling historic bazaars while sampling iconic Rajasthani delicacies like Dal Baati Churma, Pyaaz Kachori, and Laal Maas—all comfortably within your ₹15,000 budget.

Estimated Budget Breakdown (Total: ₹15,000):

Accommodation (2 nights in a budget heritage hotel/hostel): ₹4,000
Food & Dining (Authentic local eateries and street food): ₹3,500
Sightseeing/Activities (Fort entry tickets & museum passes): ₹2,500
Local Transport (Auto-rickshaws, shared autos, and city buses): ₹3,000
Buffer/Miscellaneous (Water, snacks, small souvenirs): ₹2,000
Recommended Places to Visit:
Amber Fort: A stunning fusion of Hindu and Mughal architecture (Entry: approx. ₹100 for Indians).
Hawa Mahal: The iconic 'Palace of Winds' with its unique honeycombed facade (Entry: approx. ₹50).
City Palace: Still home to the royal family, showcasing incredible museums and courtyards (Entry: approx. ₹200).
Jantar Mantar: An astronomical observation site from the 18th century, a UNESCO World Heritage site (Entry: approx. ₹50).
Nahargarh Fort: Perched on the Aravalli hills, offering panoramic sunset views of the city (Entry: approx. ₹50).
Final Day-Wise Itinerary:
Day 1: The Heart of the Walled City

Morning: Arrive in Jaipur and check into your accommodation. Head straight to the Hawa Mahal to admire the architecture from the outside and take photos.
Breakfast: Grab piping hot Pyaaz Kachori and Jalebi at the legendary Rawat Mishtan Bhandar. (Estimated spend: ₹150)
Afternoon: Explore the City Palace and walk over to Jantar Mantar right next door to marvel at the giant astrological instruments.
Lunch: Enjoy a traditional thali at Lassiwala (for a legendary sweet lassi) followed by vegetarian Rajasthani thali at Sodhani Sweets. (Estimated spend: ₹300)
Evening: Wander through the vibrant Johri Bazaar and Bapu Bazaar for local sights and sounds.
Dinner: Dine at Aline House / The Tattoo Cafe overlooking Hawa Mahal for a great view and local snacks. (Estimated spend: ₹400)
Day 1 Estimated Spend: ₹2,100 (excluding hotel/transport share)
Day 2: Majestic Forts and Royal Views

Morning: Take an auto-rickshaw early to Amber Fort. Explore the grand courtyards, Sheesh Mahal (Mirror Palace), and take in the massive scale of the stronghold.
Breakfast: Stop by Anokhi Cafe or grab local stuffed parathas near the fort base. (Estimated spend: ₹200)
Afternoon: On your way back, stop for a quick photo click at Panna Meena ka Kund (historic stepwell) and Jal Mahal (Water Palace).
Lunch: Try authentic non-vegetarian Rajasthani fare like Laal Maas at Niros on M.I. Road, or stick to budget delights at Ganesh Restaurant. (Estimated spend: ₹400)
Evening: Hire an auto to go up to Nahargarh Fort to catch a breathtaking sunset over Jaipur.
Dinner: Enjoy a rooftop dinner with historic views at Padao (Nahargarh Fort) or head back down to Samrat Restaurant for dal baati churma. (Estimated spend: ₹450)
Day 2 Estimated Spend: ₹1,350 (excluding hotel/transport share)
Day 3: Museums and Local Flavors

Morning: Visit the Albert Hall Museum located in Ram Niwas Garden, showcasing extensive collections of paintings, ivory, and crystal works.
Breakfast: Try traditional Masala Chai and Bun Maska at a local roadside stall near the garden. (Estimated spend: ₹100)
Afternoon: Spend some quiet time strolling through the gardens or picking up small, budget-friendly handicrafts (like blue pottery or block-print textiles) in Tripolia Bazaar.
Lunch: Savor a final hearty meal of Gatte ki Sabzi and Bajra Roti at Shri Balkeshwar Restaurant. (Estimated spend: ₹300)
Evening: Depart from Jaipur with wonderful historic memories and a happy stomach!
Day 3 Estimated Spend: ₹550 (excluding hotel/transport share)
Practical Tips:
Best Time to Visit Sites: Reach Amber Fort and Hawa Mahal right when they open (around 8:00 AM – 9:00 AM) to beat the tourist crowds and daytime heat.
Booking Advice: Book tickets for major monuments online if available, though ticket queues for Indians are usually manageable. You do not need expensive tour guides; audio guides or a good travel blog will suffice for history.
Local Etiquette: Bargain politely when shopping in the bazaars (aim for 20-30% off the quoted starting price), and always agree on the auto-rickshaw fare before starting your journey, or better yet, use ride-hailing apps like Ola/Uber/Rapido for transparent pricing.

2. Udaipur

Me: Plan 2 days in Udaipur for 2 people, ₹12,000 total. We love lakes and architecture.

Agent: Understanding Your Request: You want a 2-day trip to Udaipur for 2 people with a total budget of ₹12,000, focusing specifically on lakes and architecture.

Trip Overview & Highlights: Welcome to the "Venice of the East"! Udaipur is a breathtaking city steeped in royal Rajputana heritage, dominated by magnificent palaces and serene, shimmering lakes. This 2-day itinerary is carefully curated to give you an immersive experience of Udaipur's majestic architecture and picturesque lakeside views, all while staying comfortably within your ₹12,000 budget.

Estimated Budget Breakdown (Total: ₹12,000 for 2 people):

Accommodation (1 night, mid-range lakeside hotel): ₹4,000
Food & Dining (Traditional Rajasthani thalis and cafe meals): ₹3,000
Sightseeing & Activities (Palace entries, boat rides): ₹2,500
Local Transport (Auto-rickshaws and shared transport): ₹1,500
Buffer / Miscellaneous (Souvenirs, water, snacks): ₹1,000
Recommended Places to Visit:

City Palace: A colossal architectural marvel blending Rajasthani and Mughal styles, offering panoramic views of Lake Pichola. (Entry: ~₹300 per person)
Jag Mandir or Boat Ride on Lake Pichola: A scenic boat cruise leading to a stunning island palace. (Boat Ride: ~₹400-₹700 per person)
Saheliyon-ki-Bari: A beautiful historic garden featuring fountains, kiosks, marble elephants, and lotus pools. (Entry: ~₹20 per person)
Lake Fateh Sagar: A gorgeous, expansive lake surrounded by hills, perfect for a peaceful evening stroll. (Free entry)
Jagdish Temple: A brilliant example of Indo-Aryan temple architecture located right in the heart of the old city. (Free entry)
Final Day-Wise Itinerary:

Day 1: Majestic Heritage & Sunset on Lake Pichola

Morning (9:00 AM - 1:00 PM): Arrive, check into your hotel, and head straight to the City Palace. Spend a few hours marveling at the intricate mirror work, courtyards, and museums.
Lunch: Dine at Udai Art Cafe near Jagdish Temple for great coffee and continental-Indian fusion bites (Approx. ₹600 for two).
Afternoon (2:30 PM - 4:30 PM): Walk down to Jagdish Temple to admire the stunning stone carvings and architectural detailing. Right after, take a stroll through the vibrant, bustling streets of the Old City.
Evening (5:00 PM - 7:30 PM): Head to the Bansi Ghat jetty for a late-afternoon boat ride on Lake Pichola, catching the golden hour light over the lake and the Taj Lake Palace.
Dinner: Enjoy a rooftop dinner overlooking the illuminated lake at Ambrai Restaurant or a budget-friendly alternative like Khamma Ghani (Approx. ₹1,200 for two).
Estimated Spend for Day 1: ₹5,820
Day 2: Royal Gardens, Lakes & Scenic Views

Morning (9:30 AM - 12:30 PM): Visit Saheliyon-ki-Bari (Garden of the Maidens) to enjoy the peaceful fountains and lush greenery. Afterward, take an auto-rickshaw to the picturesque banks of Fateh Sagar Lake.
Lunch: Try authentic local Rajasthani Thali at Manwar Restaurant near Chetak Circle (Approx. ₹700 for two).
Afternoon (2:00 PM - 4:30 PM): Take a quick trip up to Monsoon Palace (Sajjangarh) perched high on a hill for a sweeping view of Udaipur's lakes and surrounding Aravali landscape (Entry + transport: ~₹500 for two).
Evening (5:00 PM - 7:00 PM): Wind down your trip by sitting by the steps of Gangaur Ghat or Pichola Ghat, watching the local life and the sunset over the water. Grab some street-side chai and snacks.
Dinner: Light dinner at a cozy lakeside cafe like Upre by 1559 AD or HEAVEN Hill Restaurant (Approx. ₹900 for two).
Estimated Spend for Day 2: ₹5,320
Practical Tips:

Best Time to Visit Sites: Beat the midday heat and crowds by visiting the City Palace right when it opens in the morning.
Booking Advice: Pre-booking your Lake Pichola boat ride isn't strictly necessary, but buying tickets directly at the government counter at Bansi Ghat saves you commission fees from middlemen.
Local Etiquette: Udaipur is culturally rich and conservative; dress modestly (covering shoulders and knees) when visiting temples like Jagdish. Always negotiate auto-rickshaw fares beforehand or use ride-hailing apps if available.

3. Manali (missing details)

Me: Plan a trip to Manali.

Agent: Understanding Your Request: To craft the perfect Manali trip for you, could you please let me know your trip duration (number of days) and your total budget (in ₹)?

Me: 2 weeks and my budget is 30000 rupees

Agent: Understanding Your Request:
Destination: Manali
Duration: 2 Weeks (14 Days)
Budget: ₹30,000
Interests: Exploring Manali (Since you didn't specify, I will include a balanced mix of nature, adventure, local culture, and relaxation, keeping your budget strictly in mind for a slow-paced, 2-week Himalayan experience).
2. Trip Overview & Highlights
Welcome to your ultimate 2-week slow travel escape to Manali! With a two-week window, you have a rare opportunity to truly immerse yourself in the mountain lifestyle rather than just rushing through tourist spots. Your trip will feature a mix of lush pine forests, ancient wooden temples, serene mountain villages, thrilling day treks (like Solang and Jogini Waterfall), local Himachali culinary experiences, and relaxing cafe-hopping in Old Manali.

3. Estimated Budget Breakdown (Total: ₹30,000)
To make ₹30,000 last for 14 days, staying in budget-friendly hostels/homestays and eating local food is essential. Here is the estimated breakdown:

Accommodation: ₹10,500 (approx. ₹750/night for 14 nights in backpacker hostels or budget homestays)
Food & Dining: ₹8,400 (approx. ₹600/day for local dhabas, street food, and occasional cafes)
Sightseeing & Activities: ₹4,000 (Entry fees, local permits, shared cabs, and a couple of budget adventure activities like paragliding)
Local Transport: ₹4,100 (Buses, shared autos, and local roaming)
Buffer: ₹3,000 (For emergencies, medicines, or minor impulse buys)
Note: This excludes travel to and from Manali (e.g., Volvo bus tickets from Delhi), so try to book your arrival/departure transport separately if possible!
4. Recommended Places to Visit
Hadimba Temple: Ancient wooden shrine nestled in dense Dhungri van cedar forests. (Entry: Free)
Old Manali: Famous for its bohemian vibe, cafes, and old-world wooden houses. (Entry: Free)
Jogini Waterfall: A scenic trek through apple orchards leading to a majestic waterfall. (Entry: Free)
Solang Valley: Adventure hub for paragliding, zorbing, and quad biking. (Activities priced separately; entry free)
Naggar Castle: Historic heritage site offering panoramic views of the Kullu valley. (Entry: ~₹30)
Jogini & Vashisht Hot Springs: Natural sulfur springs known for therapeutic properties. (Entry: Free)
5. Final Day-Wise Itinerary
Day 1: Arrival & Settling In
Morning: Arrive in Manali, check into your hostel/homestay. Unpack and rest after the journey.
Afternoon: Stroll around the local market area to get your bearings. Grab a quick lunch at Mount View Restaurant.
Evening: Walk through the cedar forests near the Club House. Dinner at Johnson’s Cafe (budget-friendly section) or a local dhaba.
Estimated Spend: ₹1,200
Day 2: Exploring Old Manali
Morning: Wake up slow and explore the winding lanes of Old Manali. Visit the ancient Manu Temple.
Afternoon: Lunch at Dylan’s Toast & Roast (great for coffee and pancakes).
Evening: Watch the sunset from a riverside cafe and enjoy live acoustic music if available. Dinner: Local street momos and thukpa.
Estimated Spend: ₹800
Day 3: Temples & Nature
Morning: Visit the iconic Hadimba Temple surrounded by towering pine trees. Walk down to the nearby Ghatotkach Tree Temple.
Afternoon: Lunch at a local Himachali Rasoi in the main market to try traditional Siddu.
Evening: Visit the Tibetan Monastery and shop for prayer wheels and local handicrafts. Dinner at Chopsticks Restaurant.
Estimated Spend: ₹900
Day 4: Trek to Jogini Waterfall
Morning: Take a local auto/bus to Vashisht village. Begin the scenic 2-hour trek to Jogini Waterfall passing through apple orchards.
Afternoon: Enjoy a picnic lunch near the waterfall. Head back down to Vashisht.
Evening: Soothe your trekking muscles at the Vashisht Hot Sulphur Springs. Dinner at a rooftop cafe in Vashisht.
Estimated Spend: ₹600
Day 5: Solang Valley Adventure
Morning: Take a shared cab early to Solang Valley. Try out adventure sports like zorbing or a short ATV ride (skip expensive ones if budget is tight).
Afternoon: Pack your own lunch or eat at the valley dhabas (try Maggi with mountain views).
Evening: Head back to Manali. Relax at your hostel. Dinner: Thali at a local budget eatery.
Estimated Spend: ₹1,200 (includes transport & basic activity)
Day 6: Naggar Castle Day Trip
Morning: Catch a local bus to Naggar (approx. 45 mins away). Explore the historical Naggar Castle and its art gallery.
Afternoon: Lunch near the castle overlooking the Kullu valley. Visit the Nicholas Roerich Art Gallery.
Evening: Take a local bus back to Manali. Quiet dinner and early night.
Estimated Spend: ₹650
Day 7: Rest & Slow Day
Morning: Sleep in. Enjoy a lazy breakfast at your accommodation.
Afternoon: Read a book, journal, or sketch in a quiet corner of Old Manali. Lunch at a bakery.
Evening: Walk along the Beas River listening to the water rush past. Dinner: Simple home-style meal at a local mess/homestay.
Estimated Spend: ₹500
Day 8: Jogni & Local Village Walk
Morning: Explore the lesser-known upper trails of Old Manali leading towards Shanag village.
Afternoon: Packed lunch amidst nature. Experience quiet mountain village life away from crowds.
Evening: Return to the town center. Try local bakery items. Dinner at a budget Himachali dhaba.
Estimated Spend: ₹600
Day 9: Gulaba Viewpoint
Morning: Take a shared vehicle towards the Rohtang/Gulaba route (subject to permit availability and budget; if too costly, stick to lower viewpoints like Marhi). Enjoy breathtaking valley views.
Afternoon: Return to Manali for lunch.
Evening: Explore the local market for woolen souvenirs and dry fruits (buy sparingly to stay on budget). Dinner: Local noodles.
Estimated Spend: ₹1,000
Day 10: Lamadugh Trek (Day 1 of light trekking)
Morning: Pack a day bag and start the gentle day trek to Lamadugh, winding through thick pine and maple forests.
Afternoon: Reach the alpine meadow of Lamadugh for lunch with a view of the Indrasan peak.
Evening: Trek back down before dark. Treat yourself to a hearty dinner.
Estimated Spend: ₹500
Day 11: Cultural Immersion & Photography
Morning: Visit local village schools or interact with artisans crafting traditional items.
Afternoon: Lunch at a quiet cafe. Try local trout fish if budget permits, or stick to vegetarian Himachali thali.
Evening: Sunset photography session near the Beas River bridge. Dinner at the hostel.
Estimated Spend: ₹700
Day 12: Manu Temple & Hidden Alleys
Morning: Revisit Manu Temple for a peaceful morning meditation or quiet time.
Afternoon: Hunt for hidden thrift shops and bookstores in Old Manali. Lunch at a cozy corner cafe.
Evening: Sit by a bonfire (if arranged by your hostel) and chat with fellow travelers. Dinner: Hostel-cooked meal.
Estimated Spend: ₹600
Day 13: Souvenir Shopping & Memory Making
Morning: Leisurely walk through the Tibetan market for budget-friendly winter accessories, incense, and keychains.
Afternoon: Farewell lunch at your favorite cafe from the trip.
Evening: Pack your bags and write down memories of your 2-week Himalayan journey. Dinner: Comfort food at a local eatery.
Estimated Spend: ₹800
Day 14: Departure
Morning: Check out of your accommodation. Grab a final cup of Chai.
Afternoon: Head to the bus stand for your return journey home.
Estimated Spend: ₹400 (Local transit to bus stand/snacks)
6. Practical Tips
Best Time to Visit Sites: Start early in the morning for treks and sightseeing to avoid midday crowds and sudden afternoon weather changes.
Booking Advice: Since you are staying for 2 weeks, try booking your first 2–3 nights in advance, and then negotiate a weekly/long-stay rate directly with hostels or homestays to save money!
Local Etiquette: Always dress modestly when visiting local temples (cover your shoulders and knees) and take off your shoes where required. Respect local customs and always ask permission before photographing village elders.
Water & Sustainability: Carry a reusable water bottle to avoid buying plastic bottles; most cafes and homestays offer safe drinking water refill options.

Screenshots are included in the repository
