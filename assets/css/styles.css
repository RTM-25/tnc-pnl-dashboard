// TNC (Tote&Carry) P&L Dashboard JavaScript
// Repository: tnc-pnl-dashboard
// Version 1.0

// Tab switching functionality
function switchTab(tabName) {
    // Hide all tabs
    document.querySelectorAll('.tab-content').forEach(tab => {
        tab.classList.remove('active');
    });
    
    // Remove active class from all buttons
    document.querySelectorAll('.tab-button').forEach(button => {
        button.classList.remove('active');
    });
    
    // Show selected tab
    document.getElementById(tabName + '-tab').classList.add('active');
    
    // Add active class to clicked button
    event.target.classList.add('active');
    
    // Initialize charts for the active tab
    if (tabName === 'overview') {
        initializeOverviewCharts();
    } else if (tabName === 'costs') {
        initializeCostCharts();
    }
}

// Chart configuration
Chart.defaults.color = '#9ca3af';
Chart.defaults.borderColor = 'rgba(255, 255, 255, 0.1)';
Chart.defaults.font.family = '-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif';

// Initialize Overview Charts
function initializeOverviewCharts() {
    // Monthly Trend Chart
    const monthlyCtx = document.getElementById('monthlyTrendChart');
    if (monthlyCtx) {
        new Chart(monthlyCtx.getContext('2d'), {
            type: 'bar',
            data: {
                labels: ['Jan 25', 'Feb 25', 'Mar 25', 'Apr 25', 'May 25', 'Jun 25', 'Jul 25'],
                datasets: [{
                    label: 'Monthly Net Income',
                    data: [-78775, -42274, -50979, 20671, 42912, 74326, -18025],
                    backgroundColor: function(context) {
                        const value = context.parsed.y;
                        return value < 0 ? 'rgba(239, 68, 68, 0.7)' : 'rgba(16, 185, 129, 0.7)';
                    },
                    borderColor: function(context) {
                        const value = context.parsed.y;
                        return value < 0 ? 'rgba(239, 68, 68, 1)' : 'rgba(16, 185, 129, 1)';
                    },
                    borderWidth: 2,
                    borderRadius: 6
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                layout: {
                    padding: {
                        left: 10,
                        right: 10,
                        top: 10,
                        bottom: 10
                    }
                },
                plugins: {
                    legend: {
                        display: false
                    },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                const value = context.parsed.y;
                                const label = value < 0 ? 'Loss' : 'Profit';
                                return `${label}: $${Math.abs(value).toLocaleString()}`;
                            }
                        }
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        grid: {
                            color: 'rgba(255, 255, 255, 0.05)'
                        },
                        ticks: {
                            callback: function(value) {
                                return '$' + (value/1000).toFixed(0) + 'k';
                            }
                        }
                    },
                    x: {
                        grid: {
                            display: false
                        },
                        ticks: {
                            maxRotation: 45,
                            minRotation: 45
                        }
                    }
                }
            }
        });
    }
    
    // Revenue Chart
    const revenueCtx = document.getElementById('revenueChart');
    if (revenueCtx) {
        new Chart(revenueCtx.getContext('2d'), {
            type: 'line',
            data: {
                labels: ['Jan 25', 'Feb 25', 'Mar 25', 'Apr 25', 'May 25', 'Jun 25', 'Jul 25'],
                datasets: [
                    {
                        label: 'Gross Sales',
                        data: [832000, 756000, 698000, 1423000, 892000, 945000, 871000],
                        borderColor: '#ef4444',
                        backgroundColor: 'rgba(239, 68, 68, 0.1)',
                        tension: 0.4,
                        fill: true
                    },
                    {
                        label: 'Net Sales',
                        data: [656000, 596000, 551000, 1122000, 703000, 745000, 687000],
                        borderColor: '#10b981',
                        backgroundColor: 'rgba(16, 185, 129, 0.1)',
                        tension: 0.4,
                        fill: true
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        position: 'top',
                        labels: {
                            padding: 15,
                            usePointStyle: true
                        }
                    },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                return context.dataset.label + ': $' + (context.parsed.y/1000).toFixed(0) + 'k';
                            }
                        }
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        grid: {
                            color: 'rgba(255, 255, 255, 0.05)'
                        },
                        ticks: {
                            callback: function(value) {
                                return '$' + (value/1000).toFixed(0) + 'k';
                            }
                        }
                    },
                    x: {
                        grid: {
                            display: false
                        }
                    }
                }
            }
        });
    }
}

// Initialize Cost Charts
function initializeCostCharts() {
    // Cost Trends Chart
    const costTrendsCtx = document.getElementById('costTrendsChart');
    if (costTrendsCtx) {
        new Chart(costTrendsCtx.getContext('2d'), {
            type: 'bar',
            data: {
                labels: ['Jan 25', 'Feb 25', 'Mar 25', 'Apr 25', 'May 25', 'Jun 25', 'Jul 25'],
                datasets: [
                    {
                        label: 'COGS',
                        data: [262000, 238000, 220000, 448000, 281000, 296000, 275000],
                        backgroundColor: 'rgba(239, 68, 68, 0.8)'
                    },
                    {
                        label: 'Marketing',
                        data: [190000, 173000, 160000, 325000, 204000, 216000, 199000],
                        backgroundColor: 'rgba(59, 130, 246, 0.8)'
                    },
                    {
                        label: 'Operations',
                        data: [115000, 105000, 97000, 197000, 123000, 130000, 121000],
                        backgroundColor: 'rgba(16, 185, 129, 0.8)'
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        position: 'top',
                        labels: {
                            padding: 15,
                            usePointStyle: true
                        }
                    },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                return context.dataset.label + ': $' + (context.parsed.y/1000).toFixed(0) + 'k';
                            }
                        }
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        stacked: true,
                        grid: {
                            color: 'rgba(255, 255, 255, 0.05)'
                        },
                        ticks: {
                            callback: function(value) {
                                return '$' + (value/1000).toFixed(0) + 'k';
                            }
                        }
                    },
                    x: {
                        stacked: true,
                        grid: {
                            display: false
                        }
                    }
                }
            }
        });
    }
    
    // Cost per Order Chart
    const costPerOrderCtx = document.getElementById('costPerOrderChart');
    if (costPerOrderCtx) {
        new Chart(costPerOrderCtx.getContext('2d'), {
            type: 'doughnut',
            data: {
                labels: ['COGS', 'Marketing', 'Operations', 'Shipping', 'Loan', 'Discounts', 'Fees', 'Profit/Loss'],
                datasets: [{
                    data: [46.67, 32.82, 20.31, 27.00, 12.46, 24.92, 3.40, -54.58],
                    backgroundColor: [
                        'rgba(239, 68, 68, 0.8)',
                        'rgba(59, 130, 246, 0.8)',
                        'rgba(16, 185, 129, 0.8)',
                        'rgba(139, 92, 246, 0.8)',
                        'rgba(220, 38, 38, 0.8)',
                        'rgba(245, 158, 11, 0.8)',
                        'rgba(156, 163, 175, 0.8)',
                        'rgba(239, 68, 68, 0.4)'
                    ],
                    borderWidth: 2,
                    borderColor: '#0a0a0a'
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        position: 'right',
                        labels: {
                            padding: 15,
                            font: {
                                size: 12
                            }
                        }
                    },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                const value = context.parsed;
                                const label = context.label;
                                return `${label}: $${Math.abs(value).toFixed(2)}`;
                            }
                        }
                    }
                }
            }
        });
    }
}

// Initialize charts when page loads or tabs change
function initializeCharts() {
    // Destroy existing charts to prevent memory leaks
    Chart.helpers.each(Chart.instances, function(instance) {
        instance.destroy();
    });
    
    // Initialize based on active tab
    const activeTab = document.querySelector('.tab-content.active');
    if (activeTab) {
        const tabId = activeTab.id;
        if (tabId === 'overview-tab') {
            setTimeout(initializeOverviewCharts, 100);
        } else if (tabId === 'costs-tab') {
            setTimeout(initializeCostCharts, 100);
        }
    }
}

// Handle window resize for chart responsiveness
let resizeTimer;
window.addEventListener('resize', function() {
    clearTimeout(resizeTimer);
    resizeTimer = setTimeout(function() {
        initializeCharts();
    }, 250);
});

// Initialize charts on page load
window.addEventListener('load', function() {
    initializeCharts();
});

// Touch-friendly mobile enhancements
if ('ontouchstart' in window) {
    document.body.classList.add('touch-device');
    
    // Add touch feedback to clickable elements
    const clickables = document.querySelectorAll('.tab-button, .metric-card, .cost-card, .insight-card, .month-card');
    clickables.forEach(function(element) {
        element.addEventListener('touchstart', function() {
            this.style.opacity = '0.8';
        });
        element.addEventListener('touchend', function() {
            this.style.opacity = '1';
        });
    });
}

// Improve mobile scrolling for tab navigation
const tabNav = document.querySelector('.tab-navigation');
if (tabNav) {
    let isDown = false;
    let startX;
    let scrollLeft;
    
    tabNav.addEventListener('mousedown', function(e) {
        isDown = true;
        startX = e.pageX - tabNav.offsetLeft;
        scrollLeft = tabNav.scrollLeft;
    });
    
    tabNav.addEventListener('mouseleave', function() {
        isDown = false;
    });
    
    tabNav.addEventListener('mouseup', function() {
        isDown = false;
    });
    
    tabNav.addEventListener('mousemove', function(e) {
        if (!isDown) return;
        e.preventDefault();
        const x = e.pageX - tabNav.offsetLeft;
        const walk = (x - startX) * 2;
        tabNav.scrollLeft = scrollLeft - walk;
    });
}