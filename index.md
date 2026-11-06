                   HTML


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 8.2 — Auto-Responsive Image Gallery</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <main class="page-container">
    <header class="gallery-header">
      <h1>Curated Landscapes</h1>
      <p>An auto-responsive grid adjusting fluidly across screen viewports.</p>
    </header>

    <!-- Step 3 & 5: CSS Grid container with auto-fit minmax and gap -->
    <section class="gallery-grid">

      <!-- Step 1 & 2: Gallery Item 1 -->
      <figure class="gallery-item">
        <img 
          src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?w=800&auto=format&fit=crop&q=80" 
          alt="Mist hovering over alpine lake reflection"
        >
        <figcaption>Yosemite Valley</figcaption>
      </figure>

      <!-- Gallery Item 2 -->
      <figure class="gallery-item">
        <img 
          src="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?w=800&auto=format&fit=crop&q=80" 
          alt="Fog cascading across lush green mountain ridges"
        >
        <figcaption>Morning Mist</figcaption>
      </figure>

      <!-- Gallery Item 3 -->
      <figure class="gallery-item">
        <img 
          src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=800&auto=format&fit=crop&q=80" 
          alt="Sunlight filtering through deep forest trees"
        >
        <figcaption>Deep Woods</figcaption>
      </figure>

      <!-- Gallery Item 4 -->
      <figure class="gallery-item">
        <img 
          src="https://images.unsplash.com/photo-1518495973542-4542c06a5843?w=800&auto=format&fit=crop&q=80" 
          alt="Sun flare breaking through pine forest canopies"
        >
        <figcaption>Sunlit Canopy</figcaption>
      </figure>

      <!-- Gallery Item 5 -->
      <figure class="gallery-item">
        <img 
          src="https://images.unsplash.com/photo-1469474968028-56623f02e42e?w=800&auto=format&fit=crop&q=80" 
          alt="Warm sunlight on rolling hills and distant ranges"
        >
        <figcaption>Highland Vista</figcaption>
      </figure>

      <!-- Gallery Item 6 -->
      <figure class="gallery-item">
        <img 
          src="https://images.unsplash.com/photo-1426604966848-d7adac402bff?w=800&auto=format&fit=crop&q=80" 
          alt="Rocky mountain peaks towering above a crystal stream"
        >
        <figcaption>Granite Ridge</figcaption>
      </figure>

      <!-- Gallery Item 7 -->
      <figure class="gallery-item">
        <img 
          src="https://images.unsplash.com/photo-1511497584788-87676104235f?w=800&auto=format&fit=crop&q=80" 
          alt="Forest edge enveloped in dense autumn morning fog"
        >
        <figcaption>Autumn Shroud</figcaption>
      </figure>

      <!-- Gallery Item 8 -->
      <figure class="gallery-item">
        <img 
          src="https://images.unsplash.com/photo-1472214103451-9374bd1c798e?w=800&auto=format&fit=crop&q=80" 
          alt="Golden hour light spilling over wide agricultural hills"
        >
        <figcaption>Sunset Meadows</figcaption>
      </figure>

    </section>
  </main>

</body>
</html>



                       CSS


/* --- Global Reset & Page Setup --- */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  background-color: #0f172a;
  color: #f8fafc;
  line-height: 1.5;
  padding: 3rem 1.5rem;
}

.page-container {
  max-width: 1300px;
  margin: 0 auto;
}

.gallery-header {
  text-align: center;
  margin-bottom: 2.5rem;
}

.gallery-header h1 {
  font-size: 2.25rem;
  font-weight: 800;
  letter-spacing: -0.02em;
}

.gallery-header p {
  color: #94a3b8;
  margin-top: 0.5rem;
  font-size: 1rem;
}

/* ================= STEPS 3 & 5: AUTO-RESPONSIVE GRID ================= */
.gallery-grid {
  display: grid;
  /* 
    Step 3: auto-fit with minmax
    - 'auto-fit': creates as many tracks as can fit in the row
    - 'minmax(260px, 1fr)': each item is at least 260px wide, 
      stretching up to 1fr to fill leftover row space evenly
  */
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  
  /* Step 5: Consistent spacing between rows and columns */
  gap: 1.5rem;
}

/* ================= STEPS 2 & 4: GALLERY ITEM & IMAGE STYLING ================= */
.gallery-item {
  position: relative;
  border-radius: 12px;
  overflow: hidden;
  background-color: #1e293b;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.3);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  aspect-ratio: 4 / 3;             /* Keeps all cards perfectly uniform in size */
}

.gallery-item:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 24px -4px rgba(0, 0, 0, 0.5);
}

.gallery-item img {
  /* Step 4: Full width with object-fit cover to prevent stretching/distortion */
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  display: block;
  transition: transform 0.3s ease;
}

.gallery-item:hover img {
  transform: scale(1.05);          /* Subtle zoom effect on hover */
}

/* Optional Caption Overlay */
.gallery-item figcaption {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 1.5rem 1rem 0.75rem;
  background: linear-gradient(to top, rgba(15, 23, 42, 0.85), transparent);
  color: #ffffff;
  font-size: 0.9rem;
  font-weight: 600;
  letter-spacing: 0.02em;
}