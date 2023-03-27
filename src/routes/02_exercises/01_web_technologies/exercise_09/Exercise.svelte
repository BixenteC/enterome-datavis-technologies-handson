<script>
    const radius = 2;
    const result = calculateCircumference(radius).toFixed(2);

    function calculateCircumference(r) {
        return 2 * Math.PI * r
    }
</script>

<p>The circumference of a circle with radius {radius} m is {result} m.</p>