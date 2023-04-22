<script>
    // Dimensions
    const width = 600;
    const height = 300;
    const margin = { top: 10, right: 10, bottom: 30, left: 60 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    const data = [
      { service: "Netflix", viewers: 2.9 },
      { service: "Amazon Prime Video", viewers: 1.3 },
      { service: "Disney+", viewers: 2.1 },
      { service: "Hulu", viewers: 0.9 },
      { service: "Apple TV", viewers: 1.1 },
      { service: "Rakuten", viewers: 0.4 }
    ];

    import {scaleLinear, scaleBand} from "d3-scale";
    const yscale = scaleLinear()
      .domain([0, 3])
      .range([0,innerHeight]);
    
    const uniques = [...new Set(data.map(v => v.service))]
    const xscale = scaleBand()
        .domain(uniques)
        .range([0, innerWidth])

    import {axisBottom, axisLeft} from "d3-axis"
    import {select} from "d3-selection"
    function xAxisBuilder(handle) {
      const xAxis = axisBottom(xscale)
      xAxis(select(handle))
    }
    function yAxisBuilder(handle) {
      const xAxis = axisLeft(yscale)
      xAxis(select(handle))
    }
  </script>
  
  <!-- setting a viewBox and max-width allows the SVG to shrink but not grow! -->
  <svg viewbox="0 0 {width} {height}" style="max-width: {width}px">
    <g transform={`translate(${margin.left},${margin.top})`}>
      {#each data as dp}
        <rect x={xscale(dp.service)} y={30} width="30" height={yscale(dp.viewers)} style="fill:rgb(0,0,255);stroke-width:3;stroke:rgb(0,0,0)" />
      {/each}
    </g>
    <g transform="translate({30},{15})" use:xAxisBuilder></g>
    <g transform="translate({30},{40})" use:yAxisBuilder></g>
  </svg>
  